---
title: "Introduction"
teaching: 15
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What is the purpose of quantitative data analysis in the humanities?
- When is it meaningful to use quantitative data analysis in humanities research?
- What kinds of operations can be performed in quantitative data analysis? 
- How can these operations be performed using Python programming?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Learn the basic principles and methods of quantitative data analysis for the humanities, regardless of your programming experience
- Understand which aspects of different types of datasets can be analyzed quantitatively in humanities research
- Learn how to perform basic analyses on various types of data using Python
- Understand the fundamental principles of writing Python scripts

::::::::::::::::::::::::::::::::::::::::::::::::


## 1.1. Why take this lesson?

This lesson is designed for absolute beginners in digital humanities research. Its goal is to help 
humanities scholars understand when, why, and how programming can be a valuable tool for data 
analysis in their work.

By the end of this lesson, you will have learned the basic principles of data analysis with a focus 
on quantitative research in the humanities using Python. You will be better equipped to determine 
whether incorporating programming and quantitative methods is meaningful for analyzing your 
research data. You’ll also be able to evaluate whether digitizing, processing, and publishing 
existing analog data could benefit your own research and contribute to the broader 
scholarly community.

## 1.2. Where does this lesson fit within the broader spectrum of the so-called “digital humanities”?

In the field commonly known as digital humanities, there are generally two major directions you can pursue:

1. **Work at a GLAM institution (Gallery, Library, Archive, Museum)**, where you digitize texts, images, 
and objects, and create or enrich digital catalogs for them. In this area, skills such as data management, 
knowledge of metadata standards, and understanding the FAIR principles are particularly valuable.

2. **Analyze data** gathered by yourself, other individuals, or institutions to derive insights 
that go beyond the capacity of human time or intellect due to the large volume of data. 
This is the domain of data analysis for humanities research — and this is where we will focus.


::::::::::::::::::::::::::::::::::::::: discussion
### Critical Reflection

Although the term "digital scholarship" is becoming increasingly widespread and popular, I avoid 
using it for several reasons:

1. What exactly does "digital" mean in this context? Does simply using a computer to create text, 
images, diagrams or tables transform "analog" scholarship into a "digital" one?

2. Is "digitality" — however it's defined in this context — a method, a tool, or something that 
could give rise to entirely new areas of study, such as the so-called "digital humanities"?

Instead of the vague term "digital scholarship," I prefer to use "quantitative data analysis." 
By "quantitative data analysis," I refer to a range of methods, including:

- Counting
- Comparing
- Searching
- Pattern recognition
- Classification
- Graphical representation

Quantitative data analysis is a task that can be automated using a computer. It can be performed 
with existing software designed for specific analysis tasks or by writing your own code using a programming 
language. In this lesson, we will be taking the second approach, using Python.
:::::::::::::::::::::::::::::::::::::::::::::::::::

## 1.3. When is it legitimate to practice quantitative data analysis?

In humanities research, quantitative data analysis is only logical and legitimate when:

- **It reveals new insights:** This method should uncover information that was previously unknown. If your 
research merely confirms what is already well-established, it lacks value. For example, we already know 
that women have historically been underrepresented in the documentation of human achievements. If we take 
a book on the history of art, create a list of all the artists mentioned, count how many are women, and 
conclude that female artists are less frequent in the book than male artists, our effort provides no 
new knowledge.

- **The data is too extensive for manual analysis:** The data to be analyzed is so vast that it is either 
impossible for human intellect to process it in a reasonable time frame, or it would require an impractical 
amount of resources for individuals to analyze it. For instance, counting how many of the 50 country names in a 
list belong to African Countries does not require programming; it can easily be done by an individual. 
However, analyzing large datasets, like millions of records, would require quantitative methods.


:::::::::::::::: caution
### Caution!

Avoid the temptation to overuse "digital analysis"! In today’s academic environment, there is a temptation 
to include “digital analysis” in grant proposals or PhD theses simply to make them sound modern and sophisticated. 
It's crucial not to fall into this trap and produce work that, in the end, won't be meaningful or taken seriously. 
Remember: merely adding a table or graph to your research doesn’t automatically make you a digital humanist 
or a quantitative data analyst. Always think of the points above and ask yourself whether it is insightful and 
meaningful to perform quantitative data analysis using programming or software and call it "research with 
digital methods".
::::::::::::::::::

## 1.4. What do we do, when we perform quantitative data analysis?

### Types of Data in Digital Humanities

Data used for quantitative analysis can take various forms, including:

- Tabular data (containing text, numbers, dates, etc.)
- Text
- Images
- Sound
- Audiovisual data

### Workflow for Quantitative Humanities Research

When conducting quantitative research in the humanities using Python, the typical workflow involves the 
following steps:

- Acquiring the data
- Initiating a Python script
- Loading the data into the script
- Performing operations such as exploring and cleaning the data as well as counting, comparing, searching, 
pattern recognition, classification, or visual representation
- Generating new knowledge from these processes
- Documenting the insights gained
- Presenting the insights in the context of a scientific research

### Required Knowledge for Data Analysis in the Humanities

To effectively analyze data in quantitative humanities research, it is important to have the following knowledge:

- A solid understanding of the data itself and how computers interpret and process it
- Clear insight into the specific aspects of the data to be analyzed and the type of knowledge or insights 
one aims to extract
- The ability to interact with computers to produce meaningful results — this requires proficiency in a 
programming language or familiarity with relevant software tools.

::::::::::::::::::::::::::::::::::::: keypoints 

- Determine whether the type and volume of your research data, as well as your research question, 
justify the use of quantitative data analysis. Avoid performing quantitative data analysis merely for 
the sake of having done something "digital"! 

- If you choose to pursue quantitative data analysis, consider what insights you want to extract 
from your data and how you can achieve this using Python programming.

::::::::::::::::::::::::::::::::::::::::::::::::

