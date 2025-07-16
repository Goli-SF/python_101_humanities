---
title: "Analyzing Text Data"
teaching: 120
exercises: 8
---

:::::::::::::::::::::::::::::::::::::: questions 

- What quantitative analysis operations can be performed on data composed of literary 
texts?
- How can these operations be translated into Python code?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Learn how to perform word frequency analysis on literary texts. 
- Learn how to perform keyword in context analysis on literary texts.
- Learn how to perform collocation analysis on literary texts. 
- Learn how to measure lexical diversity in a literary canon.
::::::::::::::::::::::::::::::::::::::::::::::::

In the previous episode, we worked with tabular data and performed three
core operations often used in quantitative humanities research: *counting*, *searching*,
and *visualizing*. In this episode, we'll apply similar operations to text
data. However, as you’ll see, because text fundamentally differs from tabular
data, we’ll take a completely different approach, using distinct Python libraries
and syntax to carry out these analytical tasks. 

To save the data locally on your computer, create a directory named
`data` in your working directory. Inside the `data` directory, create two
more directories named `marlowe` and `shakespeare`. Download the works by
each playwright from the GitHub links provided in the **Summary and
Setup** episode, and save them in the corresponding folders you’ve
just created.

In jupyter notebook, go ahead and save the path to each directory in a variable 
like this: 


``` python
shakespeare_path = './data/shakespeare'
marlowe_path = './data/marlowe'
```

In this episode, we’ll learn how to perform the following types of
text analysis using Python:

1. Word frequency analysis
2. Keyword-in-context analysis
3. Collocation analysis
4. Measuring lexical diversity

## 1. Word Frequency Analysis

Word frequency analysis is a foundational method in computational literary studies that 
involves counting how often individual words appear in a text or a collection of texts.
By quantifying language in this way, scholars can identify patterns, emphases, and 
stylistic tendencies with empirical precision.

This method can serve several purposes in literary research:

- It can reveal recurring themes or motifs by highlighting which words are most 
frequently used, offering insight into a text’s dominant concerns or rhetorical 
strategies. 
- It can also be used to compare the linguistic style of different authors, genres, or historical
periods, helping to map changes in diction, tone, or subject matter over time.

In studies of individual works, frequency analysis can assist in tracking narrative
focus or character development by examining how often certain names, places,
or concepts appear across a text.

Beyond individual texts, word frequency analysis can also support authorship attribution,
genre classification, and the study of intertextuality. 

In this episode, we focus on two English playwrights from the 16th century:
William Shakespeare (1564–1616) and Christopher Marlowe (1564–1593). 
We'll explore which words were
most frequently used in nine of Shakespeare’s plays and four of Marlowe’s,
all included in our dataset. This analysis will help us gain insight into
the themes and rhetoric of some of the most influential English plays written
in 16th-century England.

### Step 1: Loading the dataset into the script

Unlike the previous episode, where the dataset was stored in a single `.csv`
file, the dataset for this episode is stored in thirteen separate `.txt` files.
To store multiple texts in a single Python variable, we can construct
a *Python dictionary*.

:::::::::::::::::::::::::::::::::::::::::: spoiler
#### What is a Python dictionary?

Python dictionaries are enclosed in curly brackets: **{ }**.
A Python dictionary is a built-in data structure used to store pairs of related information. 
One part of the pair is called the *key*, and the other part is the *value*. 
Each key is linked to a specific value, and you can use the key to quickly access the 
value associated with it. A Python dictionary is structured exactly like a linguistic
dictionary: just as you look up a word in a linguistic dictionary to find its definition, 
you can store values under keys in a Python dictionary to be able to use the keys to 
retrieve the values later. 

Here’s how you might define a Python dictionary:

``` python
my_vacation_plan= {
    'budget': 100,
    'destination': 'Johannesburg',
    'accomodation': 'Sunset Hotel',
    'activities': ['hiking', 'swimming', 'biking'],
    'travel by plane': TRUE
}
```

In a Python dictionary, both keys and values can be a variety of data types, 
but with some important rules:

##### Keys:

There are two main things to know about keys:

1. They must be unique: You can’t have two identical keys in the same dictionary.
2. They must be immutable: This means they have to be data types that cannot change.

Valid key types include:

- Strings (e.g., 'budget')
- Numbers (e.g., 1, 3.14)
- Tuples (e.g., (1, 2)), as long as the tuple itself doesn’t contain mutable objects

You cannot use lists, dictionaries, or other mutable types as keys.

##### Values:

Values can be any type of Python object, including:

- Strings
- Numbers
- Lists
- Booleans
- Functions
- Even other dictionaries or complex objects

Python places no restriction on the types of values you can store.
::::::::::::::::::::::::::::::::::::::::::::::::::

We’re going to create two dictionaries: one for Marlowe’s plays, and one
for Shakespeare’s. The keys in each dictionary will be the names of the
`.txt` files — which correspond to the play titles — and the values will be the
complete texts of the plays. First, let's build a list of keys for
each dictionary:

``` python
import os

shakespeare_files = [f for f in os.listdir(shakespeare_path)]
marlowe_files = [f for f in os.listdir(marlowe_path)]

print("File names corresponding to Shakespeare:")
for file in shakespeare_files: 
    print ("*", file)
print()
print("File names corresponding to Marlowe:")
for file in marlowe_files: 
    print ("*", file)
```

![](fig/output_13.png)

::::::::::::::::::::::::::::::::::::::: discussion
#### Let's analyze the code line by line

In the above code, we're defining two lists: `shakespeare_files` and `marlowe_files`.

:::::::::::::::::::::::::::::::::::::::::: spoiler
#### What is a Python list?

A list in Python is a type of data structure used to store multiple items in a 
single variable. Lists can hold different types of data like numbers, strings, 
or even other lists. Items in a list are ordered, changeable (mutable), 
and allow duplicate values. Python lists are enclosed in square brackets: **[ ]**.

A Python list could look like this: 

```python
my_list = ['apples', 'oranges', 12, [4, 5, 6], 'bananas']
```
::::::::::::::::::::::::::::::::::::::::::::::::::

```
import os
```
This line imports Python’s built-in `os` module, which provides functions for 
interacting with the operating system. This includes functions to work with 
files and directories.

```
shakespeare_files = [f for f in os.listdir(shakespeare_path)]
```
This is a list comprehension, which is a short way to create a new list using 
a `for` loop.

:::::::::::::::::::::::::::::::::::::::::: spoiler
#### What is a for loop?

A for loop is used in Python to repeat an action for every item in a group 
(like a list). You can think of it as a way to go through a collection of 
things one by one and do something with each item. Here’s a basic idea:

```
for item in group:
    do something with item
```

The loop takes one item from the group, does something with it, then moves on 
to the next, until there are no more items left.
::::::::::::::::::::::::::::::::::::::::::::::::::

- `os.listdir(shakespeare_path)` calls a function named `listdir()` from the 
`os` module. It takes the path to a directory (given in `shakespeare_path`) 
and returns a list of all the names of files and folders inside that directory.

- `for f in os.listdir(shakespeare_path)` is a `for` loop. It goes through each 
item in the list returned by `os.listdir(shakespeare_path)`. For each item 
(each filename), it temporarily gives it the name `f`. So, `f` is a variable 
that holds each filename one by one. 

- The list comprehension `[f for f in os.listdir(shakespeare_path)]` basically 
says: "“Take each `f` (each filename) from the directory, and put it into a new list."
That new list is then assigned to the variable `shakespeare_files`.

`marlowe_files` is another list that is created through the exact same process. 

Having created these lists, we proceed to print their items one by one, again 
using a `for` loop. Notice how the `for` loop is being implemented here as compared 
to the list comprehension above. Can you see the logic behind its syntax?

:::::::::::::::::::::::::::::::::::::::::::::::::::






<span style="color:red">WE ARE HERE </span>






::::::::::::::::::::::::::::::::::::: keypoints 
- Formulate appropriate quantitative research questions when working with 
data composed of literary texts.
- Learn about dictionaries, lists and for loops in Python.
- Get to know and use the Python library spaCy.
- Perform word frequency analysis using spaCy. 
- Perform collocation analysis using spaCy.
- Measure lexical diversity in a body of text. 
::::::::::::::::::::::::::::::::::::::::::::::::

