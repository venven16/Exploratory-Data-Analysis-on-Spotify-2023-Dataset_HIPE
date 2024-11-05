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


### Basic Descriptive Statistics 

**1. What are the mean, median, and standard deviation of the streams column?** 

**Solution:** 

**Function: `spotify['streams'] = pd.to_numeric(spotify['streams'], errors = 'coerce')`**  

![image](https://github.com/user-attachments/assets/a9f15289-a45f-4ca4-89b7-81f9aeb29e75)

**Note: I searched about this code because the data type of streams is in object, and I'm not sure how I will manipulate it.**  

**Description:** This code changes the values in the Spotify DataFrame's streams column to a numeric data type. Substituting NaN for any non-numeric values, errors =' coerce' makes handling inconsistent or erroneous data during analysis or computations simpler. This stage guarantees that mathematical operations and visualizations may appropriately use the streams column. 

**Function: `mean_streams = spotify['streams'].mean()`**

![image](https://github.com/user-attachments/assets/3fbddb74-525f-4b6c-aed9-85e3ddd9ac09)

**Description:** This code determines the average (mean) number of streams in the Spotify DataFrame's streams column and outputs the outcome. It provides a summary metric that reflects the average number of streams by calculating the mean, which sheds light on the overall popularity of the songs in the dataset.

**Function:** **`median_streams = spotify['streams'].mean()`**

![image](https://github.com/user-attachments/assets/fbb0bd5a-e40e-404a-a6b8-e2e5afaa1bb0)

**Description:** This code calculates the median number of streams in the streams column of the spotify DataFrame and prints the result. The median represents the middle value when the stream counts are sorted in ascending order, providing a robust measure of central tendency less affected by extreme values or outliers than the mean. This helps better understand the typical streaming performance of songs in the dataset.

**Function: `std_streams = spotify['streams'].std()`** 

![image](https://github.com/user-attachments/assets/f83b7338-258d-450d-9e9d-a9992ea3b35c)

**Description:** This code determines and outputs the standard deviation of the Spotify DataFrame's streams column. The standard deviation measures the stream counts' degree of variance or disorder. Whereas a lower standard deviation implies that the stream numbers are nearer the mean, a higher standard deviation shows that they are dispersed over a larger range. This metric reveals the consistency of streaming performance across the dataset's various tracks.

#### Output 

![image](https://github.com/user-attachments/assets/615029b1-e803-4e8d-93c2-43bd8a450593)


**2. What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?**

**Solution:**

**Function: `print(spotify['released_year'].describe())`**

![image](https://github.com/user-attachments/assets/f4af6ec5-96b5-4b6d-981b-614a6f4e9fe6)

**Description:** This code summarizes the descriptive statistics for the Spotify DataFrame's released_year column. Information such as the release years' count, mean, minimum, maximum, and quartiles (25%, 50%, and 75%) are returned by invoking the `.describe()` function. The summary provides insights into trends or ranges of song releases and aids in comprehending the dataset's release year distribution.

**Function: `print(spotify['artist_count'].describe())`**

![image](https://github.com/user-attachments/assets/96bde568-951e-4717-8128-2ce2e0f4cb56)

**Description:** The `artist_count` column in the `spotify` DataFrame is statistically summarized by this code, which shows the count, mean, minimum, maximum, and quartiles. This data aids in comprehending the distribution of artists linked to each entry, which may reveal patterns in the dataset's solo or collaborative performances.

#### Output 

![image](https://github.com/user-attachments/assets/6fbd9c0a-e67a-4eb9-8e05-93ccad59c940)

##### Graph for `released_year` 

**Function: `plt.figure(figsize=(12, 5))`**

**Description:** It creates a new figure and sets up the area for subplots by setting its size to 12 by 5 inches.

**Function: `plt.subplot(1, 2, 1)`**

**Description:** It specifies the first subplot in a 1x2 grid layout, designating the first of two adjacent positions for this plot. 

**Function: `sns.histplot(spotify['released_year'], bins=10, kde=True)`**

**Description:** The released_year column is histogrammed with 10 bins, and a kernel density estimate (KDE) curve is superimposed to generate a smooth line that depicts the data distribution.






































































