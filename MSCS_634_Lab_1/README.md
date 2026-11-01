# MSCS 634 — Lab 1: Data Visualization, Preprocessing, and Statistical Analysis

**Student:** Shawn
**Course:** MSCS 634 — Data Mining
**Assignment:** Lab 1: Data Visualization, Data Preprocessing, and Statistical Analysis Using Python in Jupyter Notebook

## Purpose

The purpose of this lab was to practice working with data using Python in Jupyter Notebook. I used Pandas, NumPy, and Matplotlib to look at a dataset, create graphs, clean up missing information, and calculate statistics.

This lab helped me understand how to prepare data before analyzing it and how graphs and statistics can help identify patterns.

## Dataset

For this assignment, I used a Spotify and YouTube dataset that was included in the course materials.

The original dataset contains **20,718 rows and 10 columns**. It includes information about songs, artists, albums, YouTube views, likes, comments, and Spotify streams.

I chose this dataset because it has different types of information that I could compare and use for the assignment.

The project includes these files:

* `Spotify_Youtube_Sample.csv` — The original dataset.
* `Spotify_Youtube_Processed.csv` — The dataset after cleaning and processing.
* `MSCS_634_Lab_1_Shawn.ipynb` — My Jupyter Notebook containing the Python code and results.
* `screenshots/` — Screenshots showing the results of each part of the assignment.
* `requirements.txt` — The Python libraries needed to run the notebook.

## Data Visualization

I created four different graphs to help me better understand the dataset.

### 1. Bar Chart

The bar chart compares how many songs came from albums, singles, and compilations.

I found that about **72% of the songs came from albums**, while 24.2% were singles and 3.8% were compilations.

This showed me that most of the songs in the dataset were from albums.

### 2. Scatter Plot

The scatter plot compares YouTube views and Spotify streams.

I noticed that songs with more YouTube views usually had more Spotify streams. The correlation was about **0.602**, which shows a moderate relationship.

However, this wasn't true for every song. Some songs performed better on one platform than the other.

### 3. Histogram

The histogram shows how YouTube views are spread across the songs.

The average number of views was about **93.9 million**, but the median was only about **14.5 million**.

This tells me that a smaller number of really popular songs had much higher view counts, which brought the average up.

### 4. Box Plot

The box plot compares YouTube views between albums, singles, and compilations.

Songs from albums had the highest median views at about **15.8 million**. Singles were next at 11.3 million, followed by compilations at 9.6 million.

I also noticed that the number of views varied quite a bit within each group.

## Data Preprocessing

After creating the graphs, I worked on cleaning and preparing the dataset.

### Missing Values

I checked the dataset for missing information.

Some songs were missing views, likes, comments, or streaming numbers.

To fix this, I filled in missing numerical values using the median for each column. For the columns containing yes-or-no answers, I used the most common answer.

After cleaning the data, I checked again and found that there were **no missing values left**.

### Duplicate Records

I checked whether any rows were exact duplicates.

There were **0 duplicate rows**, so I didn't need to remove anything.

The dataset still contained all 20,718 rows after this step.

### Outliers

I used the IQR method to identify songs with unusually high or low YouTube views.

The results showed **2,713 outliers**, which was about 13.1% of the dataset.

After removing these from the cleaned dataset, I had **18,005 rows remaining**.

One thing I learned was that an outlier doesn't always mean something is wrong. Some songs are simply much more popular than others, so I kept the original dataset as well.

### Data Reduction

Next, I reduced the size of the dataset by randomly selecting 25% of the remaining songs.

I also removed four columns that weren't needed for the final calculations.

This reduced the dataset from 18,005 rows and 10 columns to **4,501 rows and 6 columns**.

Using a smaller dataset made it easier to work with, although it also meant that some information wasn't included in the final analysis.

### Data Scaling and Discretization

I used Min-Max scaling to change the numerical values to a range between 0 and 1.

I also separated the songs into three groups based on their YouTube views:

* **Low:** 1,501 songs
* **Medium:** 1,500 songs
* **High:** 1,500 songs

This helped me organize the songs based on their view counts while keeping the original numbers available for calculations.

## Statistical Analysis

For this part of the assignment, I used Python to calculate different statistics.

I started with `.info()` and `.describe()` to get an overview of the final dataset.

I then calculated the minimum, maximum, mean, median, and mode for views, likes, comments, and streams.

I also calculated the range, quartiles, IQR, variance, and standard deviation to see how much the numbers varied between songs.

### What I Found

One thing I noticed was that the averages were usually much higher than the median values.

For example, in the final dataset, the average number of YouTube views was about **26.5 million**, while the median was about **9.9 million**.

This showed me that some songs had much higher numbers than most of the others.

I also compared the numerical columns using a correlation matrix.

The strongest relationship was between **YouTube views and likes**, with a correlation of about **0.74**.

The relationship between YouTube views and Spotify streams was weaker in the final dataset, with a correlation of about **0.33**.

This showed me that while some numbers are related, they don't always increase together.

## Challenges and What I Learned

One of the biggest challenges in this lab was deciding how to handle missing values and outliers.

I wanted to clean the data without removing information that might still be useful.

For example, some songs had extremely high YouTube views, but that doesn't necessarily mean the numbers were incorrect. I kept the original dataset so I could still compare it with the cleaned version.

I also learned that changing or reducing a dataset can affect the results. The correlations from the original dataset were different from those calculated after cleaning and reducing it.

Overall, this lab helped me better understand how to use Python to work with data. I got more practice creating graphs, cleaning datasets, and using statistics to find patterns.

## How to Run the Notebook

To run this project:

1. Make sure Python and Jupyter Notebook are installed.
2. Open the project folder.
3. Open Command Prompt in that folder.
4. Install the required Python libraries using:

```bash
py -m pip install -r requirements.txt
```

5. Start Jupyter Notebook using:

```bash
py -m notebook
```

6. Open `MSCS_634_Lab_1_Shawn.ipynb`.
7. Run the notebook cells from top to bottom.

Make sure `Spotify_Youtube_Sample.csv` is in the same folder as the notebook.

Running the notebook will also create the processed dataset file.

## Screenshots

I included screenshots showing the results of each part of the assignment.

| Screenshot | Description                                              |
| ---------- | -------------------------------------------------------- |
| 01         | Loading the dataset and displaying the first five rows   |
| 02         | Bar chart comparing album types                          |
| 03         | Scatter plot comparing YouTube views and Spotify streams |
| 04         | Histogram showing YouTube view distribution              |
| 05         | Box plot comparing album types                           |
| 06         | Missing values before and after cleaning                 |
| 07         | Duplicate detection                                      |
| 08         | Outlier detection and removal using IQR                  |
| 09         | Data reduction before and after                          |
| 10         | Data scaling and discretization                          |
| 11         | General overview using info() and describe()             |
| 12         | Minimum, maximum, mean, median, and mode                 |
| 13         | Range, quartiles, IQR, variance, and standard deviation  |
| 14         | Correlation matrix                                       |

All screenshots are saved in the `screenshots` folder.

## Conclusion

This lab gave me hands-on practice using Python for data analysis.

I learned how to load a dataset, create graphs, handle missing information, identify outliers, and calculate different statistics.

The biggest thing I learned was that preparing the data is just as important as analyzing it. The changes made during cleaning can affect the final results, so it's important to understand what those changes do.

I feel more comfortable working with datasets in Jupyter Notebook after completing this assignment.
