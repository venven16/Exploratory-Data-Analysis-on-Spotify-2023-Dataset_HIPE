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

![image](https://github.com/user-attachments/assets/6e00a9cc-e30a-416d-9d32-b460c416d943)

**Function: `plt.figure(figsize=(12, 5))`**

**Description:** It creates a new figure and sets up the area for subplots by setting its size to 12 by 5 inches.

**Function: `plt.subplot(1, 2, 1)`**

**Description:** It specifies the first subplot in a 1x2 grid layout, designating the first of two adjacent positions for this plot. 

**Function: `sns.histplot(spotify['released_year'], bins=10, kde=True)`**

**Description:** The released_year column is histogrammed with 10 bins, and a kernel density estimate (KDE) curve is superimposed to generate a smooth line that depicts the data distribution.

**Function: `plt.title("Distribution for Released Year")`**

**Description:** It establishes the first plot's title to outline its contents.

**Function: `plt.subplot(1, 2, 2)`**

**Description:** Place this plot next to the first subplot by moving to the second subplot slot in the 1x2 grid.

**Function: `sns.boxplot(x = spotify['released_year'])`**

**Description:** It creates a box plot with the spread, median, and any outliers for the released_year column.

**Function: `plt.title("Box Plot for Released Year")`**

**Description:** It sets the second plot's title to indicate that it is the box plot for the year that was released.

**Function: `plt.tight_layout()`**

**Description:** Modifies the distance between subplots to create a neat, non-overlapping arrangement.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

##### Graph for `artisit_count`

![image](https://github.com/user-attachments/assets/5adee19f-1119-4bdc-a4e1-4d8817ed5b75)

**Function: `plt.figure(figsize=(12, 5))`**

**Description:** It creates a new figure and sets up the area for subplots by setting its size to 12 by 5 inches.

**Function: `plt.subplot(1, 2, 1)`**

**Description:** It specifies the first subplot in a 1x2 grid layout, designating the first of two adjacent positions for this plot. 

**Function: `sns.histplot(spotify['artist_count'], bins=10, kde=True)`**

**Description:** It displays the distribution form of the data by plotting a kernel density estimate (KDE) curve and a histogram of the artist_count column with 10 bins.

**Function: `plt.title("Distribution for Artist Count")`**

**Description:** It sets the first subplot's title to clarify that the artist_count distribution is displayed.

**Function: `plt.subplot(1, 2, 2)`**

**Description:** Place this plot next to the first subplot by moving to the second subplot slot in the 1x2 grid.

**Function: `sns.boxplot(x = spotify['artist_count'])`** 

**Description:** It creates a box plot for artist_count, which aids in displaying the data's median, spread, and any outliers.

**Function: `plt.title('Box Plot of Artist Count')`**

**Description:** It specifies that the second subplot is a box plot for artist_count in its title.

**Function: `plt.tight_layout()`**

**Description:** Modifies the distance between subplots to create a neat, non-overlapping arrangement.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

#### Output for `released_year` 

![image](https://github.com/user-attachments/assets/feca01b6-c2df-4c7d-aaa9-fd637fa88c9d)

**Explanation:** The distribution of song release years in the dataset is shown in this picture using a box plot on the right and a histogram on the left. The histogram indicates a right-skewed distribution where recent releases predominate, which reveals that most songs were released in the last few years, with a notable concentration in the 2020s. With a peak close to the most recent years, the Kernel Density Estimate (KDE) curve validates this concentration. The box plot on the right shows the variability and central tendency, with the median year near the most recent period. Compared to the new releases, the many outliers on the left are songs from earlier decades (before the 2000s). This graphic indicates that the dataset is biased toward newer songs, with older releases being exceptions rather than the norm.

#### Output for `artist_count` 

![image](https://github.com/user-attachments/assets/ac45bf8c-3580-4054-8b4a-1662c6665ac4)

**Explanation:** The distribution of the "artist_count" variable is shown in this image, which indicates that most songs only have one artist and that the number decreases when more artists are added. Solo performances are more prevalent, while collaborations are less common, as indicated by the histogram and KDE curve (left) showing a left-skewed distribution. With a few outliers for songs with four or more performers, the box plot (right) displays the median for a single artist. Overall, only a few songs feature many artists, mostly by solo musicians.


### Top Performers  

**1. Which track has the highest number of streams? Display the top 5 most streamed tracks.**'

**Function: `top_five_tracks = spotify.sort_values(by = 'streams', ascending = False).head(5)`**

![image](https://github.com/user-attachments/assets/a958aa19-23eb-4ec7-aa9a-eaedc9f6c67e)

**Description:** This line places the most streamed tracks at the top of the Spotify DataFrame by sorting them by the 'streams' column in descending order. The top five rows, which correspond to the top five most-streamed tracks, are then chosen.

**Function: `print("The Top 5 Most Streamed Tracks in Spotify for 2023: ")` `print(top_five_tracks[['track_name', 'streams']])`**

![image](https://github.com/user-attachments/assets/14b8c72c-d09d-40eb-b273-47c2c63ba3e5)

**Description:** The output is introduced with a title message printed by this code snippet, which states that the top 5 most-streamed tunes in 2023 are represented by the results below. From the top_five_tracks DataFrame, it shows only the 'track_name' and 'streams' columns, highlighting the names and stream counts of these top tracks.

#### Output

![image](https://github.com/user-attachments/assets/d596bfca-afc4-4ce3-8f78-d3db65b47d4b)

**2. Who are the top 5 most frequent artists based on the number of tracks in the dataset?**

**Function: `top_artists = spotify['artist(s)_name'].value_counts().head(5)`**

![image](https://github.com/user-attachments/assets/56456abf-41e1-41f2-b761-05243c9ebdf5)

**Description:** The top five most often listed artists in the `spotify` DataFrame are identified by the line of code `top_artists = spotify['artist(s)_name'].value_counts().head(5)`. The `value_counts()` function is used to count the instances of each artist's name in the `'artist(s)_name'` column, and `head(5)` is applied to obtain the top five artists with the most track counts. The outcome, which is kept in `top_artists`, offers information about the most well-known artists in the collection. 

**Function: `print(f"The Top 5 Most Frequent Artist Based on the Number of Tracks: \n") print(top_artists)`**

![image](https://github.com/user-attachments/assets/9e5d0caa-2de7-4946-96c3-4c93912102c8)

**Description:** An output introducing the top five musicians with the most tracks is displayed by the code snippet `print(f"The Top 5 Most Frequent Artists Based on the Number of Tracks: \n")` followed by `print(top_artists)`. Context is provided by the first line using an f-string, and these artists' names and track counts are printed in the second line using the `top_artists` variable. The results are presented in an easy-to-read style.







 










 


















































































































































