---
title: Setup
---

:::::::::::::::: callout
### What background knowledge do you need for this lesson?

1. Basic acquaintance with Python: you should know how to import Python packages and load data into your code.
You also need basic familiarity with Python syntax. 
2. Basic mathematical background: you need a basic understanding of statistics and probabilities. 
3. Curiosity to learn more about Python programming, statistics and data storytelling
::::::::::::::::::

## Dataset

The dataset we are working with in this lesson originates from [Kaggle](https://www.kaggle.com/datasets/levyedgar44/income-and-happiness-correction). 
If you wish to save the the dataset on your computer, go ahead and download the 
[Income and Happiness Correlation dataset](data/income_happiness_correlation.csv) and save it to your working directory. 
Otherwise, you can directly load it into your code later using the following link:

```
https://raw.githubusercontent.com/carpentries-incubator/stat_inf_data_vis/main/episodes/data/income_happiness_correlation.csv
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