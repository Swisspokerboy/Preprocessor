# PreProHelper
A nice handy tool to quickly preprocess datasets.

<img src = "https://imgur.com/tla9Hk3.png" />

## Motivation 

In my young datascience carreer, I have spent quite some time with preprocessing datasets. I noticed that I was doing the same tedious tasks over and over again, which became boring and time consuming. Therefore I created a nice little tool to help anybody with preprocessing csv files for machine learning. I'm still working on it as I want to integrate many more functionalties, but it can be used already nonetheless. 


## Main functionalities

To illustrate the basic funcionalities of the PreProHelper, the syntax *Columnname: (Columnentry, Columnentry, Columnentry)* is used. So for example *Animals: ("Dog", "Cat", "Mouse", "Bird")* would indicate a column with the Name *Animals* and the entries *"Dog", "Cat", "Mouse" and "Bird"*.

Also, one might notice that there are arrows pointing either to the right or left hand side below the various textboxes. These just indicate in which direction the column is going to be transformed. So if one selects a column in the *Categorical Columns* textbox and then clicks on the "---->" below, the selected column is transformed into a dummy column. Vice vera, if one clicked on  "<----" the slected column would turn into a numerical column. Therefore, I call these functions *Arrow Functions*.

### Arrow functions

**Numerical to Categorical**
Changes the numbers in a column to strings.

Example: 
*DayOfTheWeek: (1, 2, 7, 3)* becomes *DayOfTheWeek: ("1", "2", "7", "3")*

**Categorical to Numerical**
Labelencodes the strings in a column to numbers.

Example: 
*Animals: ("Cat", "Dog", "Mouse", "Cat")* becomes *Animals: (0, 1, 2, 0)*.

**Categorical to Dummy**
One-hot encodes all unique values in a column and creates a separate column for each value.

Example: 
*Animals: ("Dog", "Mouse", "Cat", "Mouse")* becomes *Dog: (1, 0, 0, 0)* and *Cat: (0, 0, 1, 0)* and *Mouse: (0, 1, 0, 1)*

**Dummy to Categorical**
Creates a single column out of multiple dummy encoded columns. 

Example: 
*Dog: (1, 0, 0, 0, 0)* and *Cat: (0, 0, 1, 0, 1)* becomes *Animals: ("Dog", "Unknown", "Cat", "Unknown", "Cat")*.

**Dummy to Boolean**
Changes the 1 and 0 in a column to True and False. 

Example: 
*isAnimal: (1, 0, 1, 0, 1)* becomes *isAnimal: (True, False, True, False, True)*

**Boolean to Dummy**
Changes the True and False in a column to 1 and 0. 

Example: 
*isAnimal: (True, False, True, False, True)* becomes *isAnimal: (1, 0, 1, 0, 1)*


## Setup:

**Running the file:**
The setup is fairly simple, since it is only one python file "PreproHelper.py" which one needs to run. After running the file, a new window will open, which the user can then use to preprocess his/her dataset. 

The file can either be run directly in any IDE such as Pycharm or Visualstudio or it can be run through the terminal/command line by cd'ing to the corresponding directory and then running the file (ex. python PreproHelper.py). 

**Installing packages/dependencies:**
The file needs a few packages in order to run. They are all listed in the *requirements.txt* file.
To install all the necessary dependencies, use pip in the terminal/command line  by first cd'ing to the directory where you put *requirements.txt* and the running: 

pip install -r requirements.txt

## Description:

**Import dataset:**

Type in the name of the dataset in the directory you want to import (ex: mydataset.csv). If you want to change the directory, please click on the button Change Dir.  

<img src="https://imgur.com/6uJdq2t.png"/>

Note: Currently only csv's are supported. Other file types will be implemented shortly. 


**Overview:**


