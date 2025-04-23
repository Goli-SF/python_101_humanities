---
title: "Analyzing Tabular Data"
teaching: 45
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What quantitative analysis operations can be performed on tabular data?
- How can these operations be translated into Python code?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Learn how to initiate the analysis of tabular data
- Understand which aspects of a tabular dataset can be analyzed quantitatively
- Learn to break down the analysis into smaller tasks, think in terms of computer logic, 
and translate these tasks into code
- Develop proficiency in using the Python library Pandas for tabular data analysis
- Learn to use the Python library Plotly to visualize tabular data

::::::::::::::::::::::::::::::::::::::::::::::::

Let’s take on the role of an art historian in this chapter and analyze the MoMA dataset 
introduced in the “Summary and Setup” section. We’ll assume that we are completely 
unfamiliar with the dataset, its contents, structure, or potential usefulness for our 
research. The first step would be to look at this dataset and get familiar with its 
shape, dimension and different aspects. This initial stage of investigation is known 
as *exploratory data analysis*.

To begin, we first need to open an IDE (Integrated Development Environment), select the 
programming language we’ll use, and load the dataset into the environment to start 
working with it. In this case, we’ll be using Jupyter Notebook as our IDE and Python 
as our programming language.

## Step 1 - Importing the Necessary Python Libraries

Modern computers operate using only ones and zeros — binary code. These binary digits can 
be combined to represent letters, numbers, images, and all other forms of data. At the 
most fundamental level, this is the only type of information a computer can process.

However, when you're writing code to analyze data or build applications, you don’t want 
to start from scratch — managing raw binary data or even working solely with basic characters 
and numbers. That would be extremely time-consuming and complex. Fortunately, others 
have already done much of this foundational work for us. Over the years, developers have 
created collections of pre-written code that simplify programming. You can think of these 
collections as toolboxes containing functions and methods that perform complex tasks with 
just a line or two of code. In Python, these toolboxes are called *libraries*.

Some Python libraries come built into the language, while others must be installed separately. 
Most external libraries can be easily installed via the [terminal](https://swcarpentry.github.io/shell-novice/) 
using a tool called `pip`.

Many Python libraries have quirky or creative names — part of the fun and culture of the 
programming world! For example, there's a library called `BeautifulSoup` for working with 
web data, and another called `pandas` for data analysis. Sometimes the name hints at the 
library's purpose, and sometimes it doesn’t — but you’ll get used to them over time. 
As you gain experience, you'll learn what each library is for, the tools it provides, 
and when to use them.

To use a library in your code, you first need to ensure it is installed on your computer. 
Then, you must import it into your script. If the library's name is long or cumbersome, 
you can assign it a shorter alias when importing it. For instance, in the example below, 
the `pandas` library is imported and abbreviated as `pd`. While you're free to choose any 
abbreviation, many libraries have common conventions that help make your code more readable 
to other programmers. In the case of `pandas`, `pd` is the widely recognized standard.

```python
import pandas as pd
```

## Step 2 - Loading the Data into Your Code

### Understand the data type

The MoMA dataset we will be working with is stored in a `.csv` file. Go ahead and download it 
from the link provided in the “Summary and Setup” section. 

CSV stands for "comma-separated values." When you double-click to open the file, the name 
makes perfect sense: it contains information arranged in rows, with each value in a row 
separated by a comma. Essentially, it’s a way to represent a table using a simple text file.

Each line in a CSV file corresponds to a row in the table, and each comma-separated value 
on that line represents a cell in the row. The first line often contains headers — the 
names of the columns — which describe what kind of data is stored in each column. For 
instance, a CSV file containing student information might include headers like "Name", "Age", "Grade", and "Email".

Because CSV files are plain text, they’re easy to create and read using basic tools 
like text editors or spreadsheet programs. They’re also widely supported by programming 
languages and data analysis tools, making them a popular and convenient format for storing 
and exchanging tabular data.

The data you want to analyze is typically stored either locally on your computer or hosted 
online. Regardless of where it’s located, the first step in working with it is to load it 
into your code so you can analyze or manipulate it. 

### Store the data in a variable

When you load data into your code, you should store it in a *variable*. A variable functions 
like a container that can contain any type of data that you think of. For example, I can 
create a variable called `a_number` and store a number in it, like this:

``` python
a_number = 12
print (a_number)
```

I can also store a string (a sequence of characters, including letters, numbers, and 
other symbols) in a variable, which I'll call `a_string`, like this:"

``` python
a_string= "This is a string, consisting of numbers (like 13), letthers and other signs!"
print (a_string)
```
Notice that you should put the value of the string inside double or single quotes, but you shouldn't do it for numbers. 

:::::::::::::::: callout
#### When naming a variable, note that:

- Only letters (a-z, A-Z), digits (0-9), and underscores (_) are allowed.
- The name cannot start with a digit.
- No spaces or special characters (like !, @, #, etc.) are allowed.
- Variable names are case-sensitive. For example, `myvar` and `MyVar` are two different variables.
- You cannot use Python reserved keywords like: `if`, `else`, `for`, `class`, `return`, etc. as variable names. 

::::::::::::::::::

<span style="color:red">WE ARE HERE</span>

::::::::::::::::::::::::::::::::::::: keypoints 
- Formulate appropriate research questions when working with tabular data
- Identify the quantitative analysis methods best suited to answering these questions
- Break down the analysis into smaller tasks, translate them into computer logic, and 
implement them in code
::::::::::::::::::::::::::::::::::::::::::::::::

