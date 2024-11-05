# Exploratory Data Analysis on Spotify 2023 Dataset

This repository contains Python codes for solving the given programming problems for this project. Full details of each solution using Python are included in this repository.

### Deliverable Explanation: 
**In this deliverable, you will perform an exploratory data analysis (EDA) on a dataset containing information about popular tracks on Most Streamed Spotify Songs 2023 (https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023Links to an external site.). This task aims to analyze, visualize, and interpret the data to extract meaningful insights.**

#### Things to do first before answering the guide question:
 
**Declaring all the libraries needed for the whole project.**

![image](https://github.com/user-attachments/assets/e1a7c135-9337-457b-bd68-a9799cd75e4c)


**Library:** **`import numpy as np`**

**Description:** A powerful Python Library for numerical computing is mostly used for managing arrays and mathematical calculations. Numerous mathematical operations and functions essential to scientific computing and data management are supported.


**Library:** **`import pandas as pd`** 

**Description:** A Library for data analysis and manipulation that simplifies working with structured data by offering data structures like DataFrames and Series. It is crucial for data science projects since it is frequently used for data preparation, cleansing, and investigation.


**Library:** **`import seaborn as sns`**

**Description:** A Matplotlib-based data visualization package was created significantly to facilitate the creation and interpretation of statistical visuals. Seaborn offers high-level functionality and aesthetic themes to make complex visualizations like heat maps and category plots easier to understand.


**Library:** **`import matplotlib.pyplot as plt`**

**Description:** A popular Python charting toolkit that provides low-level control to produce a range of static, animated, and interactive representations. It is helpful for intricate plot modification and forms the basis for various visualization libraries (such as Seaborn).


**Read the Data Set that was given to us:** 

**Function:** **`spotify = pd.read_excel('spotify-2023.xlsx') spotify`**

![image](https://github.com/user-attachments/assets/b4c9d8c6-d163-4a0d-9cd4-765ac4bb43f0)                    

**Description:** This code displays the contents of a Pandas DataFrame named `spotify` after loading data from an Excel file called `spotify-2023.xlsx`. It reads the file and arranges the data in a structured manner using `pd.read_excel`, which makes it simple to examine, work with, and display in Python. Spotify, in the end, is to declare the DataFrame needed. 

#### Output: 

![image](https://github.com/user-attachments/assets/5a319912-3c62-4e34-a33b-341d7d07b400)


## Guide Questions: 
### Overview of Dataset 

**1. How many rows and columns does the dataset contain?** 

**Solution:**

**Function:** **`spotify.shape`** 

![image](https://github.com/user-attachments/assets/3b6a2a1e-86d9-4da1-a789-18ffc75e4e54)

**Description:** The Spotify DataFrame, which holds data imported from an Excel file, has rows and columns, as indicated by this code. The number of rows (data entries) and columns (features or attributes) are indicated by the first and second values of the tuple that are returned using spotify.shape. Before conducting a more thorough analysis or visualization, it is crucial to rapidly comprehend the size and dimensionality of the dataset, which is made easier by this overview. 

#### Output 

![image](https://github.com/user-attachments/assets/9d3ec7fa-66e3-423c-8f1b-d0e68aa8e9a5)


**2. What are the data types of each column? Are there any missing values?**

**Solution:**

**Fucntion:** **`spotify.dtypes`** 

![image](https://github.com/user-attachments/assets/95bd8a28-55ad-4dc1-9bc6-f99c92f15fc9)

**Description:** The data type of each column in the Spotify DataFrame is shown by this code, which makes it easier to comprehend if the data is strings, floats, or integers.

#### Output 

![image](https://github.com/user-attachments/assets/a33ddeb0-bef6-44e8-a14d-c7c3586c4486)


**Function:** **`spotify.isnull().sum()`** 

**Description:** This code examines each Spotify DataFrame column for missing values. It counts the amount of NaN values in each column using isnull().sum(), which helps locate any missing data requiring attention.

#### Output 

![image](https://github.com/user-attachments/assets/1ba00c35-cd63-4045-9ad6-31134a3db3d0)







