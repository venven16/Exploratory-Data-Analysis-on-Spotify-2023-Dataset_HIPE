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

### Output: 

![image](https://github.com/user-attachments/assets/5a319912-3c62-4e34-a33b-341d7d07b400)


## Guide Questions: 
### Overview of Dataset 

**1. How many rows and columns does the dataset contain?** 

**Solution:**

**Function:** **`spotify.shape`** 

![image](https://github.com/user-attachments/assets/3b6a2a1e-86d9-4da1-a789-18ffc75e4e54)

**Description:** The Spotify DataFrame, which holds data imported from an Excel file, has rows and columns, as indicated by this code. The number of rows (data entries) and columns (features or attributes) are indicated by the first and second values of the tuple that are returned using spotify.shape. Before conducting a more thorough analysis or visualization, it is crucial to rapidly comprehend the size and dimensionality of the dataset, which is made easier by this overview. 

### Output 

![image](https://github.com/user-attachments/assets/9d3ec7fa-66e3-423c-8f1b-d0e68aa8e9a5)


**2. What are the data types of each column? Are there any missing values?**

**Solution:**

**Fucntion:** **`spotify.dtypes`** 

![image](https://github.com/user-attachments/assets/95bd8a28-55ad-4dc1-9bc6-f99c92f15fc9)

**Description:** The data type of each column in the Spotify DataFrame is shown by this code, which makes it easier to comprehend if the data is strings, floats, or integers.

### Output 

![image](https://github.com/user-attachments/assets/a33ddeb0-bef6-44e8-a14d-c7c3586c4486)


**Function:** **`spotify.isnull().sum()`** 

**Description:** This code examines each Spotify DataFrame column for missing values. It counts the amount of NaN values in each column using isnull().sum(), which helps locate any missing data requiring attention.

### Output 

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

### Output 

![image](https://github.com/user-attachments/assets/615029b1-e803-4e8d-93c2-43bd8a450593)


**2. What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?**

**Solution:**

**Function: `print(spotify['released_year'].describe())`**

![image](https://github.com/user-attachments/assets/f4af6ec5-96b5-4b6d-981b-614a6f4e9fe6)

**Description:** This code summarizes the descriptive statistics for the Spotify DataFrame's released_year column. Information such as the release years' count, mean, minimum, maximum, and quartiles (25%, 50%, and 75%) are returned by invoking the `.describe()` function. The summary provides insights into trends or ranges of song releases and aids in comprehending the dataset's release year distribution.

**Function: `print(spotify['artist_count'].describe())`**

![image](https://github.com/user-attachments/assets/96bde568-951e-4717-8128-2ce2e0f4cb56)

**Description:** The `artist_count` column in the `spotify` DataFrame is statistically summarized by this code, which shows the count, mean, minimum, maximum, and quartiles. This data aids in comprehending the distribution of artists linked to each entry, which may reveal patterns in the dataset's solo or collaborative performances.

### Output 

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

### Output for `released_year` 

![image](https://github.com/user-attachments/assets/feca01b6-c2df-4c7d-aaa9-fd637fa88c9d)

**Explanation:** The distribution of song release years in the dataset is shown in this picture using a box plot on the right and a histogram on the left. The histogram indicates a right-skewed distribution where recent releases predominate, which reveals that most songs were released in the last few years, with a notable concentration in the 2020s. With a peak close to the most recent years, the Kernel Density Estimate (KDE) curve validates this concentration. The box plot on the right shows the variability and central tendency, with the median year near the most recent period. Compared to the new releases, the many outliers on the left are songs from earlier decades (before the 2000s). This graphic indicates that the dataset is biased toward newer songs, with older releases being exceptions rather than the norm.

### Output for `artist_count` 

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

### Output

![image](https://github.com/user-attachments/assets/d596bfca-afc4-4ce3-8f78-d3db65b47d4b)

**2. Who are the top 5 most frequent artists based on the number of tracks in the dataset?**

**Function: `top_artists = spotify['artist(s)_name'].value_counts().head(5)`**

![image](https://github.com/user-attachments/assets/56456abf-41e1-41f2-b761-05243c9ebdf5)

**Description:** The top five most often listed artists in the `spotify` DataFrame are identified by the line of code `top_artists = spotify['artist(s)_name'].value_counts().head(5)`. The `value_counts()` function is used to count the instances of each artist's name in the `'artist(s)_name'` column, and `head(5)` is applied to obtain the top five artists with the most track counts. The outcome, which is kept in `top_artists`, offers information about the most well-known artists in the collection. 

**Function: `print(f"The Top 5 Most Frequent Artist Based on the Number of Tracks: \n") print(top_artists)`**

![image](https://github.com/user-attachments/assets/9e5d0caa-2de7-4946-96c3-4c93912102c8)

**Description:** An output introducing the top five musicians with the most tracks is displayed by the code snippet `print(f"The Top 5 Most Frequent Artists Based on the Number of Tracks: \n")` followed by `print(top_artists)`. Context is provided by the first line using an f-string, and these artists' names and track counts are printed in the second line using the `top_artists` variable. The results are presented in an easy-to-read style.

### Output 

![image](https://github.com/user-attachments/assets/f25bfe44-c7aa-4d21-b501-71b374a8923c)

### Temporal Trends 

**1. Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.**

**Function: `tracks_per_year = spotify['released_year'].value_counts().sort_index()`**

![image](https://github.com/user-attachments/assets/3dc7b8b5-cbdd-40d1-8e0e-c7faec96f1d2)

**Description:** The line of code tracks_per_year = spotify['released_year'].value_counts().sort_index() counts the number of tracks released each year in the spotify DataFrame. It accesses the 'released_year' column, uses value_counts() to tally the occurrences of each year, and applies sort_index() to arrange the results in chronological order. This creates a series called tracks_per_year that shows the distribution of track releases by year.

![image](https://github.com/user-attachments/assets/5563e279-f35f-4ff3-8bab-2b8af9b1c1e2)

**Function: `plt.figure(figsize=(12, 6))`**

**Description:** To guarantee that the plot has a distinct and suitable aspect ratio, this line generates a new figure for the plot 12 inches wide and 6 inches tall.

**Function: `sns.lineplot(data=tracks_per_year, marker='o')`**

**Description:** This line uses Seaborn's lineplot function to create a line plot. The data source is tracks_per_year, and to improve visualization, circular marks (marker='o') are added at each data point.

**Function: `plt.title('Number of Tracks Released Per Year')`**

**Description:** By setting the plot's title to "Number of Tracks Released Per Year," this line gives the visitor background information about what the graph depicts.

**Function: `plt.xlabel('Year')`**

**Description:** With this line labeling the x-axis "Year," the years of track releases are represented on the horizontal axis.

**Function: `plt.ylabel('Number of Tracks')`**

**Description:** By labeling the y-axis "Number of Tracks," this line indicates that the vertical axis shows the total number of tracks that have been released.

**Function: `plt.grid()`**

**Description:** By adding a grid to the plot and giving reference lines, this line facilitates reading and interpreting the data.

**Function: `plt.tight_layout()`**

**Description:** This line modifies the plot parts' spacing to ensure everything is aesthetically pleasing and fits nicely inside the figure area.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

#### Output

![image](https://github.com/user-attachments/assets/124f7148-f817-4dd8-a5b1-6ce761637aab)

Explanation: 


**2. Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?**

**Function: `tracks_per_month = spotify['released_month'].value_counts().sort_index()`**

![image](https://github.com/user-attachments/assets/ef549d63-c31f-4681-8007-7507dda01025)

**Description:** The number of tracks released each month in the `spotify` DataFrame is counted by the line of code `tracks_per_month = spotify['released_month'].value_counts().sort_index()`. The `'released_month'` column is accessed, the occurrences of each month are counted using `value_counts()`, and the results are arranged chronologically using `sort_index()`. A sorted Series displaying the distribution of track releases per month will be contained in the variable `tracks_per_month`.

**Function: `month_names = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']`**

![image](https://github.com/user-attachments/assets/46cc84ef-3786-49f3-a92b-1f6e0fd90d60)

**Description:** `month_names = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']` generates a list named month_names that includes the acronyms for the twelve months of the year. You can use this list to label month-related data or visualizations.

![image](https://github.com/user-attachments/assets/e53ca6f0-5422-4978-8e08-29bcf3bb7d8e)

**Function: `plt.figure(figsize=(10, 5))`**

**Description:** To guarantee that the plot has a distinct and suitable aspect ratio, this line generates a new figure for the plot 10 inches wide and 5 inches tall.

**Function: `plt.bar(month_names, tracks_per_month.reindex(range(1, 13), fill_value =0), color = 'red',)`**

**Description:** This line uses the bar function in Matplotlib to generate a bar chart. The months of the year are represented by the month_names label on the x-axis. Tracks_per_month provides the y-axis data, which is reindexed to guarantee that every month from January (1) to December (12) is present. Any missing months are filled in with a count of 0 using fill_value=0. Red is the color of the bars.

**Function: `plt.title('Number of Tracks Released Per Month')`**

**Description:** This line updates the bar chart's title to "Number of Tracks Released Per Month," giving the chart's meaning some context.

**Function: `plt.xlabel('Month')`**

**Description:** This line designates the x-axis as "Month," signifying that the months of the year are represented on the horizontal axis.

**Function: `plt.ylabel('Number of Tracks')`**

**Description:** This line designates the y-axis as "Number of Tracks," meaning that the vertical axis represents the number of tracks released in a given month.

**Function: `plt.tight_layout()`**

**Description:** This line modifies the plot parts' spacing to ensure everything is aesthetically pleasing and fits nicely inside the figure area.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

![image](https://github.com/user-attachments/assets/4f7abe46-3ae7-4de1-8451-15e531d4b62b)

**Function: `most_releases_month = tracks_per_month.idxmax()`**

**Description** This line uses the idxmax() function on the tracks_per_month Series to identify the month with the most track releases. The index (month number) corresponding to the highest value is returned.

**Function: `most_releases_count = tracks_per_month.max()`**

**Description:** This line uses the tracks_per_month Series' max() function to retrieve the maximum number of track releases. This value is saved in the most_releases_count variable.

**Function: `print(f"The month sees the most releases is {month_names[most_releases_month - 1]} with {most_releases_count} releases.")`**

**Description:** The results are summarized in a prepared text printed in this line. The maximum release count and the month name (accessible by indexing into month_names with most_releases_month - 1 to accommodate for zero-based indexing) are included using an f-string. The message shows how many releases occurred in a given month and which had the most releases.

#### Output

![image](https://github.com/user-attachments/assets/752bb668-f0a3-488c-969c-5b7fe959c165)

**Explanation:** The bar graph shows the number of released tracks per month in 2023. It showed that January has the highest number of tracks released. 

### Genre and Music Characteristics

**1. Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?**

**Function: `correlation_matrix = spotify[['streams', 'bpm', 'danceability_%', 'energy_%']].corr()`**

![image](https://github.com/user-attachments/assets/601ba3a5-da4b-47c1-ac08-c35620e9c334)

**Description:** The correlation matrix for the chosen numerical columns in the `spotify` DataFrame—`'streams'`, `'bpm'`, `'danceability_%'`, and `'energy_%'`—is computed by the line of code `correlation_matrix = spotify[['streams', 'bpm', 'danceability_%', 'energy_%']].corr()`. The pairwise correlation coefficients between these attributes are calculated by the `corr()` function, producing a DataFrame showing their correlations' direction and strength.

**Function: `print("Correlation Matrix between Streams and Musical Attributes: \n") print(correlation_matrix)`**

**Description:** The code snippet `print("Correlation Matrix between Streams and Musical Attributes: \n")` followed by `print(correlation_matrix)` introduces and displays the correlation matrix. The first line provides context by stating that the matrix shows the relationships between track streams and musical attributes. In contrast, the second line outputs the correlation coefficients, allowing the user to analyze these relationships.

#### Output 

![image](https://github.com/user-attachments/assets/91bc5644-2604-4b43-b367-7afb5d00757c)

**Function: `plt.figure(figsize=(18, 5))`**

![image](https://github.com/user-attachments/assets/c486a0f1-537f-4205-9ac3-7fe91d07eea8)

**Description:** To guarantee that the plot has a distinct and suitable aspect ratio, this line generates a new figure for the plot 18 inches wide and 5 inches tall.

#### Scatter plot for Streams vs. BPM

![image](https://github.com/user-attachments/assets/8fae511f-bee2-4c41-ab42-5680884c4fd6)

**Function: `plt.subplot(1, 3, 1)`**

**Description:** This line places the current plot in the first subplot (1st column) and creates a subplot in a grid layout of 1 row and 3 columns. This makes it possible to show more than one plot in a single figure.

**Function: `sns.scatterplot(x = 'bpm', y = 'streams', data = spotify, color = 'red')`**

**Description:** This line uses Seaborn's scatterplot function to generate a scatter plot. The Spotify DataFrame data is used to plot the'streams' on the y-axis against the 'bpm' (beats per minute) on the x-axis. To make the points more visible, they are dyed red.

**Function" `plt.title('Streams vs. BPM')`**

**Description:** This line changes the scatter plot's title to "Streams vs. BPM," revealing the plot's meaning.

**Function: `plt.xlabel('BPM (Beats per Minute)')`**

**Description:** This line labels the x-axis as "BPM (Beats per Minute)," clarifying that the horizontal axis represents the beats per minute of the tracks.

**Function: `plt.ylabel('Number of Streams')`**

**Description:** With this line labeling the y-axis "Number of Streams," the vertical axis is shown to be the number of streams for the tracks.

#### Ouput 

![image](https://github.com/user-attachments/assets/11a7340f-297b-46b2-a15a-02476ec20c1d)

#### Scatter plot for Streams vs. Danceability

![image](https://github.com/user-attachments/assets/b1801eea-4aef-4a7a-8c9b-0652bae421bd)

**Function: `plt.subplot(1, 3, 2)`**

**Description:** This line positions the current plot in the second subplot (2nd column) of a subplot set up in a grid layout of 1 row and 3 columns. This enables the side-by-side display of several plots in a single figure.

**Function: `sns.scatterplot(x='danceability_%', y='streams', data=spotify, color='purple')`**

**Description:** This line uses Seaborn's scatterplot function to generate a scatter plot. The Spotify DataFrame data is used to plot the 'danceability_%' on the x-axis versus the 'streams' on the y-axis. For distinction, the points are tinted purple.

**Function: `plt.title('Streams vs. Danceability')`**

**Description:** This line changes the scatter plot's title to "Streams vs. Danceability," identifying the relationship the plot is depicting.

**Function: `plt.xlabel('Danceability (in %)')`**

**Description:** This line labels the x-axis as `Danceability (in %)`, clarifying that the horizontal axis represents the beats per minute of the tracks.

**Function: `plt.ylabel('Number of Streams')`**

**Description:** With this line labeling the y-axis "Number of Streams," the vertical axis is shown to be the number of streams for the tracks.

### Output 

![image](https://github.com/user-attachments/assets/5eac8cf8-e2a4-4f3c-861d-f132566ad5d9)

#### Scatter plot for Streams vs. Energy

![image](https://github.com/user-attachments/assets/6f07f53b-79ec-4268-93a3-ea176f28972a)

**Function: `plt.subplot(1, 3, 3)`**

**Description:** This line places the current plot in the third subplot (3rd column) of a subplot set up in a grid layout of 1 row and 3 columns. This makes it possible to arrange several plots next to each other in a single figure.

**Function: `sns.scatterplot(x='energy_%', y='streams', data=spotify, color='skyblue')`**

**Description:** This line uses Seaborn's scatterplot function to generate a scatter plot. It uses data from the Spotify DataFrame to plot the 'streams' on the y-axis against the 'energy_%' on the x-axis. To distinguish this plot from the others, the dots are colored sky blue.

**Function: `plt.title('Streams vs. Energy')`**

**Description:** This line changes the scatter plot's title to "Streams vs. Energy," highlighting the correlation between energy levels and stream counts that is being shown.

**Function: `plt.xlabel('Energy (in %)')`**

**Description:** This line labels the x-axis as `Energy (in %)`, clarifying that the horizontal axis represents the beats per minute of the tracks.

**Function: `plt.ylabel('Number of Streams')`**

**Description:** With this line labeling the y-axis "Number of Streams," the vertical axis is shown to be the number of streams for the tracks.

**Function: `plt.tight_layout()`**

**Description:** This line modifies the plot parts' spacing to ensure everything is aesthetically pleasing and fits nicely inside the figure area.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

### Output 

![image](https://github.com/user-attachments/assets/ced5015b-f3fd-48f8-abe9-4053abbee57d)

**2. Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?**

![image](https://github.com/user-attachments/assets/6e77e0c3-4f4e-4c68-9512-a17b9419f886)

**Function: `dance_energy_corr = spotify['danceability_%'].corr(spotify['energy_%'])`**

**Description:** The correlation coefficient between the 'danceability_%' and 'energy_%' columns in the Spotify DataFrame is determined by this line using the corr() method. The outcome, which shows the direction and intensity of the linear relationship between danceability and energy, is recorded in the variable dance_energy_corr.

**Function: `valence_acousticness_corr = spotify['valence_%'].corr(spotify['acousticness_%'])`**

**Description:** This line uses the corr() method to determine the correlation coefficient between the 'valence_%' and 'acousticness_%' columns in the Spotify DataFrame. The outcome, which illustrates the connection between valence and acousticness, is kept in the variable valence_acousticness_corr.

**Function: `print(f"Correlation between Danceability and Energy: {dance_energy_corr:.2f}\n")`**

**Description:** This line outputs a formatted string with the determined relationship between energy and danceability. The format specification :.2f is used to round the correlation value to two decimal places, and a newline character is appended for spacing.

**Function: `print(f"Correlation between Valence and Acousticness: {valence_acousticness_corr:.2f}\n")`**

**Description:** The estimated correlation between valence and acousticness is reported in a prepared string that is printed in this line. The number is rounded to two decimal places and a newline character is added for clarity.

### Output 

![image](https://github.com/user-attachments/assets/7a3d7877-9aba-477a-81ce-db3b3a4535f7)

**Function: `plt.figure(figsize=(12, 5))`**

![image](https://github.com/user-attachments/assets/bf55602d-c589-4467-b2f1-be120d069423)

**Description:** To guarantee that the plot has a distinct and suitable aspect ratio, this line generates a new figure for the plot 12 inches wide and 5 inches tall.

#### Scatter plot for Danceability vs. Energy

![image](https://github.com/user-attachments/assets/05947e1b-dd5a-4409-a3d7-e0f20b865fa9)

**Function: `plt.subplot(1, 2, 1)`**

**Description:** For Matplotlib, the line plt.subplot(1, 2, 1) creates a subplot inside a grid layout. It places the current plot in the first subplot (1st column) and defines a grid with 1 row and 2 columns. This makes it possible to compare or present related visualizations in a straightforward manner by allowing many plots to be shown side by side within a single figure.

**Function: `sns.scatterplot(x='danceability_%', y='energy_%', data=spotify, color='pink')`**

**Description:** This line uses Seaborn's scatterplot function to generate a scatter plot. The Spotify DataFrame data is used to plot the 'danceability_%' on the x-axis versus the 'energy_%' on the y-axis. The plot's pink dots make it easy to see how the two variables are related to one another.

**Function: `plt.title('Danceability vs. Energy')`**

**Description:** This line changes the scatter plot's title to "Danceability vs. Energy," highlighting the relationship between the music' danceability and energy levels.

**Function: `plt.xlabel('Danceability (in %)')`**

**Description:** This line labels the x-axis as `Danceability (in %)`, clarifying that the horizontal axis represents the danceability in %.

**Function: `plt.ylabel('Energy (in %)')`**

**Description:** With this line labeling the y-axis "Energy (in %)," the vertical axis is shown to be the energy in %.

### Output 

![image](https://github.com/user-attachments/assets/cae12cab-bf94-43b1-89ae-a9cb28ac666a)


#### Scatter plot for Valence vs. Acousticness

![image](https://github.com/user-attachments/assets/b362cec9-35f6-4ac3-8cd7-ea984e6cad4f)

**Function: `plt.subplot(1, 2, 2)`**

**Description:** This line specifies a grid with one row and two columns for Matplotlib, setting up a subplot inside the grid layout. It allows two plots to be shown side by side in the same figure by placing the current plot in the second subplot (2nd column).

**Function: `sns.scatterplot(x='valence_%', y='acousticness_%', data=spotify, color='purple')`**

**Description:** This line uses Seaborn's scatterplot function to generate a scatter plot. The Spotify DataFrame data plots the 'valence_%' on the x-axis versus the 'acousticness_%' on the y-axis. This plot's purple points graphically depict the connection between acousticness and valence.

**Function: `plt.title('Valence vs. Acousticness')`**

**Description:** This line changes the scatter plot's title to "Valence vs. Acousticness," highlighting the relationship between the recordings' valence and acousticness levels.

**Function: `plt.xlabel('Valence (in %)')`**

**Description:** This line labels the x-axis as `Valence (in %)`, clarifying that the horizontal axis represents the valence in %.

**Function: `plt.ylabel('Acousticness (in %)')`**

**Description:** With this line labeling the y-axis "Acousticness (in %)," the vertical axis is shown to be the number acousticness in %.

**Function: `plt.tight_layout()`**

**Description:** This line modifies the plot parts' spacing to ensure everything is aesthetically pleasing and fits nicely inside the figure area.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

### Output 

![image](https://github.com/user-attachments/assets/4c15f6eb-9739-4ca9-bcff-51a5efaf389e)

### Platform Popularity 

**1. How do the numbers of tracks in spotify_playlists, deezer_playlist, and apple_playlists compare? Which platform seems to favor the most popular tracks?**

![image](https://github.com/user-attachments/assets/67ecf65f-e1d3-4c97-bb18-df3b762f0bf7)

**Function: `spotify_tracks = spotify['in_spotify_playlists'].sum()`**

**Description:** The overall number of tracks in Spotify playlists is determined by this line. It applies the sum() function, which adds up the values in the 'in_spotify_playlists' column of the Spotify DataFrame. The variable spotify_tracks contains the result.

**Function: `deezer_tracks = spotify['in_deezer_playlists'].sum()`**

**Description:** This line determines how many music are in Deezer playlists overall. Like the line before it, it retrieves the Spotify DataFrame's 'in_deezer_playlists' column and aggregates the results using the sum() method. The variable deezer_tracks contains the result.

**Function: `apple_tracks = spotify['in_apple_playlists'].sum()`**

**Description:** The overall number of tracks in Apple playlists is determined by this line. To obtain the total, it uses the sum() function on the Spotify DataFrame's 'in_apple_playlists' column. The variable apple_tracks contains the result.

![image](https://github.com/user-attachments/assets/f80f8d39-a038-40f7-8ed5-d9afcbdd09e6)

**Function: `track_counts = pd.DataFrame({
    'Platform': ['Spotify', 'Deezer', 'Apple Music'],
    'Total Tracks': [spotify_tracks, deezer_tracks, apple_tracks]})`**

**Description:** The line of code creates a Pandas DataFrame named `track_counts` to organize the total number of tracks across different music streaming platforms. It uses a dictionary where the key `'Platform'` lists the platform names `['Spotify', 'Deezer', 'Apple Music']`, and the key `'Total Tracks'` contains the corresponding total track counts `[spotify_tracks, deezer_tracks, apple_tracks]`. This DataFrame provides a clear comparison of track availability among these services.

**Function: `plt.figure(figsize=(16, 7))`**

![image](https://github.com/user-attachments/assets/253f9dac-1604-438e-8859-23509c62c002)

**Description:** To guarantee that the plot has a distinct and suitable aspect ratio, this line generates a new figure for the plot 16 inches wide and 7 inches tall.

#### Graphing the number of tracks for per platform using bar plot

**Function: `plt.bar(track_counts['Platform'], track_counts['Total Tracks'], color=['pink', 'purple', 'skyblue'])`**

**Description:** This line uses the bar function in Matplotlib to generate a bar chart. It makes use of the values from the track_counts DataFrame's Platform column for the x-axis and the Total Tracks column for the y-axis. To visually differentiate the platforms, the bars are colored with a predetermined list of hues: sky blue for Apple Music, purple for Deezer, and pink for Spotify.

**Function: `plt.title('Total Number of Tracks in Different Playlists by Different Platforms')`**

**Description:** By setting the bar chart's title to "Total Number of Tracks in Different Playlists by Different Platforms," this line places the chart's meaning in perspective.

**Function: `plt.xlabel('Platform')`**

**Description:** This line labels the x-axis as `Platform`, clarifying that the horizontal axis represents each platform.

**Function: `plt.ylabel('Total Tracks')`**

**Description:** With this line labeling the y-axis "Total Tracks," the vertical axis is shown to be the number of total tracks.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

**Function: `popularity = 5000000`**

![image](https://github.com/user-attachments/assets/68ac9791-29d2-46d9-89f8-94ebd592e598)

**Description:** It sets the standard of popularity to 5000000 streams 

![image](https://github.com/user-attachments/assets/1798e822-3fab-4da6-92c2-492787c44fbe)

**Function: `popular_tracks_spotify = spotify[spotify['streams'] > popularity]['in_spotify_playlists'].count()`**

**Description:** Only tracks whose number of streams is beyond a predetermined popularity threshold are included in the Spotify DataFrame after this line filters it. The result is then stored in the variable popular_tracks_spotify, which counts the number of tracks in the 'in_spotify_playlists' column that satisfy this requirement.

**Function: `popular_tracks_deezer = spotify[spotify['streams'] > popularity]['in_deezer_playlists'].count()`**

**Description:** This line, like the one before it, searches the Spotify DataFrame for music that have more streams than the popularity threshold. The number of times these tracks appear in the 'in_deezer_playlists' column is counted and stored in the popular_tracks_deezer variable.

**Function: `popular_tracks_apple = spotify[spotify['streams'] > popularity]['in_apple_playlists'].count()`**

**Description:** A similar pattern is used in this line, which filters the DataFrame for tracks whose streams are higher than the popularity level. It keeps track of how many tracks in the 'in_apple_playlists' column satisfy this requirement and saves the result in the popular_tracks_apple variable.

**Function: `print(f"Popular Tracks in Spotify: {popular_tracks_spotify}\n") print(f"Popular Tracks in Deezer: {popular_tracks_deezer}\n") print(f"Popular Tracks in Apple Music: {popular_tracks_apple}")`**

![image](https://github.com/user-attachments/assets/110d1b0e-8092-4145-b418-68dedde9345e)

**Description:** The number of popular tracks with streams above the popularity threshold across various platforms is printed in these three lines. The number of popular songs for Spotify, Deezer, and Apple Music is output in each line, providing a brief overview of the proportion of high-stream music in playlists on each platform. 

### Output 

![image](https://github.com/user-attachments/assets/b45fc83b-eb31-429b-8922-c30490a2297b)

### Advanced Analysis 

**1. Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?**

![image](https://github.com/user-attachments/assets/5f9fdb35-7ad2-4984-befa-0a92c576ef5a)

**Function: `key_groups = spotify.groupby('key')['streams'].agg(['mean', 'median', 'std', 'count']).reset_index()`**

**Description:** This line groups the Spotify DataFrame according to the 'key' column and computes the mean, median, standard deviation (std), and count for the'streams' column within each group. The grouped data is converted back into a standard DataFrame format using the reset_index() function, creating a new DataFrame called key_groups that contains statistics of streams by musical key.

**Function: `print(f"Statistics of Streams by Key:\n \n{key_groups}")`**

**Description:** The key_groups DataFrame, which shows the computed statistics (mean, median, standard deviation, and count) of streams for each musical key, is displayed after this line prints the title "Statistics of Streams by Key".

### Output 

![image](https://github.com/user-attachments/assets/47640529-0574-4f1b-a554-da859c92491f)

#### Graphing the distribution of streams for each key using box plot

![image](https://github.com/user-attachments/assets/63f654c8-4a37-4091-b558-3ac95f4e7fbc)

**Function: `plt.figure(figsize=(12, 5))`**

**Description:** To guarantee that the plot has a distinct and suitable aspect ratio, this line generates a new figure for the plot 12 inches wide and 5 inches tall.

**Function `sns.boxplot(x = 'key', y = 'streams', data = spotify, color = 'pink')`**

**Description:** This line uses Seaborn's boxplot function to generate a box plot. The Spotify DataFrame's 'key' and 'streams' columns are plotted on the x and y axes, respectively, to display the distribution of stream counts for each musical key. For aesthetic effect, the plot is colored pink.

**Function: `plt.title('Distribution of Streams by Key')`**

**Description:** This line changes the box plot's title to "Distribution of Streams by Key," signifying that the chart shows the central tendency and distribution of streams for every musical key.

**Function: `plt.xlabel('Musical Key')`**

**Description:** This line labels the x-axis as `Musical Key`, clarifying that the horizontal axis represents the musical keys.

**Function: `plt.ylabel('Number of Streams')`**

**Description:** With this line labeling the y-axis "TNumber of Streams," the vertical axis is shown to be the number of streams.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

### Output 

![image](https://github.com/user-attachments/assets/6d5404da-e6fa-469c-afdd-c408e22a2686)


![image](https://github.com/user-attachments/assets/c4c46604-83b3-4420-ba41-dad806b1e9e6)

**Function: `mode_groups = spotify.groupby('mode')['streams'].agg(['mean', 'median', 'std', 'count']).reset_index()`**

**Description:** This line of code computes statistics for the 'streams' column inside each mode group and groups the Spotify DataFrame according to the 'mode' column. It uses the agg() function to calculate the mean, median, standard deviation (std), and number of streams for each mode. The grouped data is then converted back into a standard DataFrame format using the reset_index() method, producing a new DataFrame called mode_groups that compiles these statistics for every mode.

**Function: `print(f"Streams statistics by mode:\n \n{mode_groups}")`**

**Description:** The headline "Streams statistics by mode," followed by the mode_groups DataFrame, is printed on this line. An overview of the differences in stream counts between musical modes is given by this output, which shows the mean, median, standard deviation, and number of streams for each mode.

### Output 

![image](https://github.com/user-attachments/assets/27341396-5a0c-48d5-8d6d-ca58367f3722)

**Explanation:** The distribution of streams by musical key is displayed in the graph. The number of streams is shown on the y-axis, while the musical key is represented on the x-axis. According to the graph, C#, F, and D are the most often used keys. B and G are the least used keys. This implies that when it comes to streaming music, there is a preference for particular musical keys.

#### Graphing the distribution of streams for each key using box plot

![image](https://github.com/user-attachments/assets/792c4c33-a807-40d0-aded-1f15d52dc89f)

**Function: `plt.figure(figsize=(12, 5))`**

**Description:** To guarantee that the plot has a distinct and suitable aspect ratio, this line generates a new figure for the plot 12 inches wide and 5 inches tall.

**Function: `sns.boxplot(x = 'mode', y = 'streams', data =s potify, color = 'purple')`**

**Description:** Plotting "mode" on the x-axis and "streams" on the y-axis using data from the Spotify DataFrame, this line uses Seaborn's boxplot function to create a box plot. This plot displays the distribution of stream counts for each musical mode, which is represented by the 'mode' column. Examples of these modes are major and minor. For clarity, the plot has been shaded purple.

**Function: `plt.title('Distribution of Streams by Mode (Major vs. Minor)')`**

**Description:** With this line, the box plot's title is changed to "Distribution of Streams by Mode (Major vs. Minor)," signifying that the plot illustrates the differences between streams in major and minor modes.

**Function: `plt.xlabel('Mode')`**

**Description:** This line labels the x-axis as `Musical Key`, clarifying that the horizontal axis represents the mode.

**Function: `plt.ylabel('Number of Streams')`**

**Description:** With this line labeling the y-axis "TNumber of Streams," the vertical axis is shown to be the number of streams.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

### Output 

![image](https://github.com/user-attachments/assets/17f4cdc6-cbd0-47c7-93e2-65c1f957f265)

**Explanation:** The distribution of streams for songs in major and minor keys is displayed in this boxplot. The boxplot indicates that songs in a minor key have a marginally higher median number of streams. While some songs in both major and minor keys have a notably higher number of streams than others, the boxplot also reveals a number of outliers (shown by circles) in the data. This implies that a song's key might not be a reliable indicator of how many streams it will get.

**2. Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.**

![image](https://github.com/user-attachments/assets/a117a242-22e5-40f5-a885-513642f6eeb6)

**Function: `spotify['total_playlists'] = (spotify['in_spotify_playlists'] + spotify['in_apple_playlists'] + spotify['in_deezer_playlists'])`**

**Description:** This line adds a new column to the Spotify DataFrame called "total_playlists," which contains the total number of playlists for each tune on Spotify, Apple Music, and Deezer. The total number of playlists a tune appears on is shown in this column.

**Function: `spotify['total_charts'] = (spotify['in_spotify_charts'])`**

**Description:** The 'in_spotify_charts' column's value is stored in a new column called 'total_charts' created by this line. It precisely records if a song is on the Spotify charts.

**Function: `artist_playlist_counts = spotify.groupby('artist(s)_name')['total_playlists'].sum().reset_index()`**

**Description:** This line combines the Spotify DataFrame by artist name ('artist(s)_name') and adds up the numbers in 'total_playlists' to determine how many playlists each artist's music is in. A new DataFrame named artist_playlist_counts contains the results.

**Function: `artist_chart_counts = spotify.groupby('artist(s)_name')['total_charts'].sum().reset_index()`**

**Description:** Similarly, this line combines the data per artist and adds up the numbers in 'total_charts' to determine each artist's total number of chart appearances. Artist_chart_counts is where the results are kept.

**Function: `artist_counts = pd.merge(artist_playlist_counts, artist_chart_counts, on = 'artist(s)_name', how = 'outer')`**

**Description:** This line creates a combined DataFrame artist_counts by combining artist_playlist_counts and artist_chart_counts on the artist name column. It does this by utilizing an outer join to include all artists from both DataFrames.

**Function: `artist_counts.columns = ['artist_name', 'total_playlists', 'total_charts']`**

**Description:** 'artist_name', 'total_playlists', and 'total_charts' are the new names for the artist_counts columns that this line sets for clarity.

**Function: `artist_counts = artist_counts.sort_values(by = 'total_playlists', ascending = False).head(10)`**

**Description:** This line selects the top 10 artists with the highest playlist counts by sorting artist_counts according to 'total_playlists' in descending order.

### Visualization of Top 10 Artist in terms of Appearances in Playlist and Charts using bar plot

![image](https://github.com/user-attachments/assets/9c874b9f-f715-4f84-81f5-23fe7f0a1887)

**Function: `plt.figure(figsize=(16, 7))`**

**Description:** To guarantee that the plot has a distinct and suitable aspect ratio, this line generates a new figure for the plot 16 inches wide and 7 inches tall.

**Function: `sns.barplot(x = 'total_playlists', y = 'artist_name', data = artist_counts, color = 'pink', label = 'Playlists')`**

**Description:** This line uses Seaborn's barplot function to construct a horizontal bar plot with 'artist_name' on the y-axis and 'total_playlists' on the x-axis. The total number of playlist appearances for each artist is represented by pink bars that are colored using data from artist_counts.

**Function: `sns.barplot(x = 'total_charts', y = 'artist_name', data = artist_counts, color = 'purple', label = 'Charts', alpha = 0.5)`**

**Description:** This line plots 'total_charts' (chart appearances) against 'artist_name' to create a second bar plot on top of the first. The purple bars are semi-transparent due to their alpha value of 0.5, which lets the pink playlist bars peek through. This makes comparisons simpler by producing a stacked effect.

**Function: `plt.title('Top 10 Artists by Total Appearances in Playlists and Charts')`**

**Description:** "Top 10 Artists by Total Appearances in Playlists and Charts," which describes the data displayed, is the plot title defined by this line.

**Function: `plt.xlabel('Total Appearances')`**

**Description:** In this line, the x-axis is labeled "Total Appearances," meaning that the number of appearances in playlists and charts is represented by the horizontal bars.

**Function: `plt.ylabel('Artist Name')`**

**Description:** This line designates the y-axis as "Artist Name," indicating that each bar corresponds to a top-10 artist.

**Function: `plt.show()`**

**Description:** Renders the graphic so the box plot and histogram can be analyzed concurrently.

### Output 

![image](https://github.com/user-attachments/assets/9210d979-f64b-4df4-8049-b6913a057bfc)

**Explanation:**  The top ten artists by total number of playlist and chart appearances are displayed in this horizontal bar chart. Taylor Swift, Ed Sheeran, and The Weeknd are the artists with the most appearances. Playlists and charts make up the two sections of the chart. A purple bar indicates the charts area, and a pink bar indicates the playlists part. Each bar's height indicates how many times the musician has performed overall. Ed Sheeran is the musician with the most appearances on charts, and The Weeknd is the artist with the most appearances on playlists.
















































































 












































































 












































 












































































 










 


















































































































































