---
title: Setup
---

:::::::::::::::: callout
### What background knowledge do you need for this lesson?

1. Basic mathematical background
2. Familiarity with quantitative research methods
2. Curiosity to learn about quantitative data analysis and Python programming
::::::::::::::::::

## Datasets

In this lesson, we will work with multiple datasets. Each dataset represents a specific 
type of data that is suited to particular methods of quantitative analysis.

### 1. Artworks from MoMA

The metadata for artworks in the [Museum of Modern Art (MoMA)](https://www.moma.org/) collection 
can be downloaded from the museum's [GitHub Repository](https://github.com/MuseumofModernArt/collection). 

Since the data in this GitHub repository is continuously updated, we will be working with a 
version previously downloaded on April 9, 2025. This version is stored in the GitHub 
repository for this lesson, ensuring that the results you see during live coding match 
exactly what is demonstrated in the lesson.

To load the data from this lesson’s repository into your code, use the following URLs:

<span style="color:red">Link to be updated.</span>

**Data for Episode 2 (Analyzing Tabular Data):**

```
https://github.com/HERMES-DKZ/python_101_humanities/blob/main/episodes/data/moma_artworks.csv
```

**Data for Episode 3 (Analyzing Text Data):**

```
https://github.com/HERMES-DKZ/python_101_humanities/blob/main/episodes/data/shakespeare

https://github.com/HERMES-DKZ/python_101_humanities/blob/main/episodes/data/marlowe
```

## Software Setup

::::::::::::::::::::::::::::::::::::::: discussion

### Python and Jupyter Notebook/Google Colab

To do the exercises in this lesson, you need an IDE (Integrated Development Environment). We recommend you use 
Jupyter Notebook or cloud-based equivalent such as [Google Colab](https://colab.google/). 

If you're using Google Colab, you don't need any installation. Just create a Google account - if you don't have one
already -, create a new Colab Notebook by clicking on <kbd>New Notebook</kbd> in the above link, and start coding. 

Otherwise, to install Jupyter Notebook and Python on your computer together, we recommend using 
[Anaconda](https://www.anaconda.com/download/success).
To do so, click on your operating system from the list below and follow the instructions. 

:::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: spoiler

### Windows

1. Open https://www.anaconda.com/download/success with your web browser.
2. Download the Anaconda for Windows installer with Python 3. (If you are not sure which version to choose, you probably want the 64-bit 
Graphical Installer *Anaconda3-...-Windows-x86_64.exe*.)
3. Install Python 3 by running the Anaconda Installer, using all of the defaults for installation *except* make sure to check 
**Add Anaconda to my PATH environment variable**.

This [video tutorial](https://www.youtube.com/watch?v=xxQ0mzZ8UvA) can help you with the installation. 

::::::::::::::::::::::::

:::::::::::::::: spoiler

### MacOS

1. Open https://www.anaconda.com/download/success with your web browser.
2. Download the Anaconda Installer with Python 3 for macOS (you can either use the Graphical or the Command Line Installer).
3. Install Python 3 by running the Anaconda Installer using all of the defaults for installation.

This [video tutorial](https://www.youtube.com/watch?v=TcSAln46u9U) can help you with the installation.


::::::::::::::::::::::::


:::::::::::::::: spoiler

### Linux

1. Open https://www.anaconda.com/download/success with your web browser.
2. Download the Anaconda Installer with Python 3 for Linux.
(The installation requires using the shell. If you aren't comfortable doing the installation yourself stop here and request help at the workshop.)
3. Open a terminal window and navigate to the directory where the executable is downloaded (e.g., `cd ~/Downloads`).
4. Type `bash Anaconda3-` and then press <kbd>Tab</kbd> to autocomplete the full file name. The name of file you just 
downloaded should appear.
5. Press <kbd>Enter</kbd> (or <kbd>Return</kbd> depending on your keyboard). You will follow the text-only prompts. 
To move through the text, press <kbd>Spacebar</kbd>. Type `yes` and press <kbd>Enter</kbd> (or <kbd>Return</kbd>) 
to approve the license. Press <kbd>Enter</kbd> (or <kbd>Return</kbd>) to approve the default location for the files. 
Type `yes` and press <kbd>Enter</kbd> (or <kbd>Return</kbd>) to prepend Anaconda to your `PATH` (this makes the Anaconda distribution the default Python).
6. Close the terminal window.

::::::::::::::::::::::::


After installing Python and Anaconda, make sure to install the Python libraries that we are using in this lesson. If you haven't installed Python libraries on your 
computer before, ask the instructors for support. 