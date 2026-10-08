# Social Media Engagement Analytics Using Python

## Project Overview

Social media platforms generate large volumes of user engagement data such as likes, comments, shares, impressions, watch time, followers, and engagement rates.

This project analyzes a **5,000-record social media engagement dataset** using Python to understand content performance, audience behavior, engagement trends, sentiment patterns, and the impact of factors such as post type, category, country, device, age, and verification status.

The project demonstrates practical skills in **Pandas, NumPy, Matplotlib, Seaborn, and Plotly**, covering the complete workflow from data cleaning and transformation to exploratory data analysis, visualization, and business insights.

---

## Project Objectives

The main objectives of this project are:

* Import and inspect social media engagement data.
* Identify and handle missing values.
* Detect and remove duplicate records.
* Correct data types and standardize categorical values.
* Validate engagement-related numerical values.
* Extract useful features such as hashtag count.
* Perform exploratory data analysis using Pandas.
* Create new analytical metrics such as engagement score.
* Perform descriptive statistical analysis.
* Analyze relationships between social media metrics.
* Create meaningful static and interactive visualizations.
* Identify important business and user behavior insights.

---

## Dataset

**Dataset Name:** `social_media_engagement_5000.csv`

### Dataset Size

* **Rows:** 5,000
* **Original Columns:** 19

### Main Variables

| Column             | Description                                  |
| ------------------ | -------------------------------------------- |
| `post_id`          | Unique identifier for each social media post |
| `user_id`          | Unique identifier for the user               |
| `posted_at`        | Date and time when the post was published    |
| `age`              | Age of the user                              |
| `gender`           | Gender of the user                           |
| `country`          | User's country                               |
| `post_type`        | Type of social media post                    |
| `post_category`    | Category of the content                      |
| `device_type`      | Device used to access the platform           |
| `likes`            | Number of likes received                     |
| `comments`         | Number of comments received                  |
| `shares`           | Number of shares received                    |
| `hashtags`         | Hashtags associated with the post            |
| `watch_time_sec`   | Watch time in seconds                        |
| `impression_count` | Number of impressions                        |
| `follower_count`   | Number of followers                          |
| `is_verified`      | Indicates whether the account is verified    |
| `engagement_rate`  | Existing engagement rate                     |
| `sentiment`        | Sentiment associated with the post           |

---

## Technologies Used

### Programming Language

* Python

### Libraries

* **Pandas** – Data manipulation and analysis
* **NumPy** – Numerical computations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization
* **Plotly** – Interactive visualizations

### Development Environment

* Google Colab
* GitHub

---

# Project Workflow

## Data Import and Setup

The dataset was imported using Pandas and initially inspected to understand its structure.

The following operations were performed:

* CSV file import
* Shape inspection
* Column inspection
* Data type checking
* Date conversion
* Initial dataset exploration

The `posted_at` column was converted into a proper datetime format for time-based analysis.

---

## Data Cleaning

### Missing Value Handling

Missing values were identified using:

```python
isnull()
isna()
```

Numerical missing values were handled using **median imputation**, while categorical missing values were handled using **mode imputation**.

Numerical fields included:

* Age
* Likes
* Comments
* Shares

Categorical fields included:

* Gender
* Sentiment

### Duplicate Handling

Duplicate records were identified using:

```python
df.duplicated()
```

Duplicate rows were removed using:

```python
df.drop_duplicates()
```

### Data Formatting

Categorical fields were standardized by:

* Removing unnecessary spaces
* Standardizing text case
* Cleaning category labels

### Numerical Validation

Engagement metrics such as likes, comments, and shares were checked for unrealistic negative values.

---

## Feature Engineering

Several new fields were created to support deeper analysis.

### Engagement Score

The engagement score was calculated as:

```text
Engagement Score = Likes + Comments + Shares
```

Python implementation:

```python
df['engagement_score'] = (
    df['likes'] +
    df['comments'] +
    df['shares']
)
```

### Calculated Engagement Rate

A calculated engagement rate was created using:

```text
Calculated Engagement Rate =
(Likes + Comments + Shares) / Impressions
```

### Hashtag Count

The number of hashtags in each post was extracted and stored as:

```text
hashtag_count
```

### Date Features

Additional date-related fields were created:

* Year
* Month
* Month Name
* Day
* Day Name
* Hour

### Log Transformation

Log-transformed metrics were also created for highly skewed numerical variables such as:

* Followers
* Impressions
* Likes

---

## Exploratory Data Analysis

Pandas was used to explore the dataset through:

* `head()`
* `tail()`
* `shape`
* `columns`
* `info()`
* `dtypes`
* `describe()`
* `value_counts()`
* `unique()`
* `nunique()`

GroupBy operations were used to analyze:

* Average likes by post type
* Average engagement by post type
* Impressions by country
* Engagement by content category
* Performance by sentiment
* Device-level behavior

A correlation matrix was also created to understand relationships between numerical variables.

---

## Statistical Analysis

Descriptive statistics were calculated for:

* Likes
* Comments
* Shares
* Watch Time
* Engagement Rate
* Follower Count

The following statistical measures were analyzed:

* Mean
* Median
* Mode
* Standard deviation
* Variance
* 25th percentile
* 50th percentile
* 75th percentile
* 90th percentile
* 95th percentile
* Skewness
* Kurtosis

This helped understand the distribution and variability of social media engagement metrics.

---

## Data Visualization

Multiple visualizations were created using Matplotlib, Seaborn, and Plotly.

### Matplotlib Visualizations

1. Likes vs Impressions – Scatter Plot
2. Daily Engagement Trend – Line Chart
3. Posts by Category – Bar Chart
4. Gender Distribution – Pie Chart
5. Age Distribution – Histogram
6. Engagement Rate – Box Plot

### Seaborn Visualizations

7. Post Type Distribution – Count Plot
8. Average Likes by Category – Bar Plot
9. Followers vs Sentiment – Violin Plot
10. Correlation Matrix – Heatmap
11. Engagement vs Device – Swarm Plot
12. Numeric Feature Relationships – Pair Plot

### Plotly Visualization

13. Interactive Daily Engagement Trend
14. Interactive Engagement Bubble/Scatter Chart

These visualizations provide both statistical and business perspectives on social media performance.

---

# Business Insights and Recommendations

## Business Insights

The Social Media Engagement Analytics project analyzed **5,000 social media records** to understand content performance, user behavior, device usage, posting time, account verification, and sentiment.

### Video Content Has the Highest Engagement

Among the different post types, **video posts** generated the highest average engagement score of approximately **12,664.59**.

This indicates that video content is highly effective at generating interactions such as likes, comments, and shares.

**Recommendation:**
Increase the proportion of video content in the social media strategy and focus on short, engaging, and relevant videos to encourage user interaction.

---

### Music Is the Best-Performing Content Category

The **music** category achieved the highest average engagement score of approximately **12,788.55**.

This suggests that music-related content has strong audience interaction in the analyzed dataset.

**Recommendation:**
Prioritize high-performing categories such as music and experiment with different formats within these categories to identify content patterns that consistently generate engagement.

---

### Brazil Has the Highest Average Engagement Rate

**Brazil** recorded the highest average calculated engagement rate at approximately **1.5369**.

This indicates that users from Brazil generated a relatively high level of interaction compared with the number of impressions received.

**Recommendation:**
Consider developing localized content and targeted campaigns for high-engagement countries. Content language, cultural preferences, and posting schedules can be customized for these audiences.

---

### Mobile Users Have the Highest Average Watch Time

Mobile users recorded the highest average watch time at approximately **4,087.83 seconds**, compared with tablet and desktop users.

The device analysis showed:

| Device  | Avg. Watch Time (sec) | Avg. Engagement |
| ------- | --------------------: | --------------: |
| Mobile  |          **4,087.83** |       12,663.19 |
| Tablet  |              3,979.74 |       12,463.28 |
| Desktop |              3,974.79 |   **12,708.56** |

Although mobile users had the highest watch time, desktop users had slightly higher average engagement.

**Recommendation:**
Optimize content primarily for mobile consumption while also ensuring desktop users receive a strong experience. Mobile-friendly video formats, captions, vertical layouts, and fast-loading content should be prioritized.

---

### Negative Sentiment Posts Have the Highest Engagement Rate

Negative sentiment posts recorded the highest calculated engagement rate of approximately **1.0383**, compared with:

| Sentiment | Posts | Avg. Engagement | Avg. Engagement Rate |
| --------- | ----: | --------------: | -------------------: |
| Negative  |   960 |   **12,731.50** |           **1.0383** |
| Neutral   | 1,527 |       12,448.16 |               0.9907 |
| Positive  | 2,513 |       12,665.80 |               0.9191 |

Negative posts generated the highest engagement rate even though positive posts represented the largest number of posts.

**Recommendation:**
Monitor negative-content engagement carefully. High engagement does not necessarily mean positive business performance. Organizations should analyze comments and reactions to determine whether negative posts represent useful discussions, complaints, controversy, or potential reputation risks.

---

### Negative Posts Generate More Engagement Than Neutral Posts

The comparison between negative and neutral content shows that negative posts generated:

* **12,731.50** average engagement
* **1,516.09** average comments
* **1,007.31** average shares
* **4,054.64 seconds** average watch time
* **50,191.96** average impressions

Neutral posts generated:

* **12,448.16** average engagement
* **1,528.40** average comments
* **996.57** average shares
* **4,031.82 seconds** average watch time
* **49,515.97** average impressions

Negative posts therefore produced higher overall engagement and slightly higher watch time and impressions.

**Recommendation:**
Use negative-content performance as a signal for understanding audience concerns and discussion topics rather than simply increasing negative content. Businesses should identify the reasons behind this engagement and use the findings to improve products, services, and communication strategies.

---

### Verified Accounts Have a Higher Engagement Rate

The analysis found that verified accounts had a higher calculated engagement rate:

* **Verified:** 1.0619
* **Non-verified:** 0.9534

However, non-verified accounts had a slightly higher average engagement score:

* **Non-verified:** 12,644.31
* **Verified:** 12,309.28

Verified accounts also had slightly higher average impressions:

* **Verified:** 50,747.34
* **Non-verified:** 49,935.29

**Recommendation:**
Account credibility may contribute to a stronger engagement rate. Businesses and creators should focus on building audience trust, maintaining consistent content quality, and developing a credible online presence rather than relying only on verification status.

---

### Younger Users Show Strong Engagement

The age-group analysis shows:

| Age Group | Posts | Avg. Engagement |
| --------- | ----: | --------------: |
| Under 18  |   448 |   **13,104.75** |
| 18–25     |   742 |       12,608.14 |
| 26–35     |   981 |       12,768.70 |
| 36–45     | 1,076 |       12,741.58 |
| 46–55     |   919 |       12,373.49 |
| 56+       |   834 |       12,261.74 |

The **Under 18** group recorded the highest average engagement score, while the **56+** group recorded the lowest.

**Recommendation:**
Segment content according to audience age. Younger audiences may respond better to highly interactive and visually engaging content, while older audiences may require different content formats and messaging approaches.

---

### Midnight Shows the Highest Average Impressions

The analysis identified **00:00 (midnight)** as the hour with the highest average impressions in this dataset.

**Recommendation:**
Test publishing content around high-performing time periods, including midnight, but validate this pattern using a larger time range before making it a permanent publishing strategy. A/B testing different posting times can help identify the most reliable engagement window.

---

# Overall Recommendations

Based on the analysis, the following recommendations can be implemented:

### 1. Prioritize Video Content

Video posts generated the highest average engagement. Organizations should increase high-quality video content and test different video formats.

### 2. Focus on High-Performing Categories

The music category achieved the highest average engagement. Similar high-performing categories should receive additional content development and promotional attention.

### 3. Optimize for Mobile Users

Mobile users recorded the highest average watch time. Content should therefore be optimized for mobile screens, particularly through vertical formats, captions, and concise video content.

### 4. Target High-Engagement Markets

Brazil recorded the highest average engagement rate. Localized content and targeted campaigns can be tested in high-performing countries.

### 5. Monitor Negative Sentiment

Negative posts produced the highest engagement rate. Instead of simply increasing negative content, businesses should investigate the topics generating negative engagement and use them to identify customer concerns and opportunities for improvement.

### 6. Build Account Credibility

Verified accounts showed a higher engagement rate. Businesses should strengthen credibility through consistent branding, reliable information, audience interaction, and professional content.

### 7. Use Age-Based Content Strategies

Engagement varies across age groups. Audience segmentation can help businesses customize content formats and messaging for different age segments.

### 8. Optimize Posting Time

Midnight recorded the highest average impressions in this dataset. Businesses should test this period against other high-performing hours before adopting it as a standard publishing schedule.

### 9. Use Data-Driven Content Planning

Rather than evaluating content only by likes, organizations should monitor multiple KPIs such as **engagement score, engagement rate, impressions, watch time, comments, and shares**.

### 10. Continuously Test and Measure

Social media performance can change over time. Regular analysis and A/B testing should be used to validate content type, category, posting time, audience segment, and device-specific strategies.

---

# Data Cleaning Summary

The project follows a structured data-cleaning workflow:

```text
Raw Dataset
     ↓
Import CSV
     ↓
Check Structure
     ↓
Check Missing Values
     ↓
Handle Missing Values
     ↓
Check Duplicates
     ↓
Remove Duplicates
     ↓
Standardize Categories
     ↓
Validate Numerical Values
     ↓
Convert Date Column
     ↓
Feature Engineering
     ↓
Clean Dataset
     ↓
Exploratory Data Analysis
```

---

# Project Structure

```text
Social-Media-Engagement-Analytics/
│
├── social_media_engagement_5000.csv
│
├── Social_Media_Engagement_Analytics.ipynb
│
├── cleaned_social_media_engagement.csv
│
└── README.md
```

---

# Skills Demonstrated

This project demonstrates practical knowledge of:

* Python Programming
* Pandas
* NumPy
* Data Cleaning
* Data Validation
* Data Transformation
* Feature Engineering
* Exploratory Data Analysis
* Descriptive Statistics
* GroupBy Analysis
* Correlation Analysis
* Data Visualization
* Matplotlib
* Seaborn
* Plotly
* Business Analysis
* Insight Generation

---

# How to Run the Project

### Step 1 – Open Google Colab

Create a new Google Colab notebook.

### Step 2 – Upload Dataset

Upload:

```text
social_media_engagement_5000.csv
```

### Step 3 – Install/Import Libraries

Run the library import cell.

### Step 4 – Execute the Notebook

Run the notebook cells sequentially from:

```text
Data Import
     ↓
Data Cleaning
     ↓
Data Exploration
     ↓
Data Wrangling
     ↓
Statistical Analysis
     ↓
Visualization
     ↓
Business Insights
```

### Step 5 – Export Cleaned Dataset

The notebook generates:

```text
cleaned_social_media_engagement.csv
```

---

# Conclusion

This project provides an end-to-end analysis of social media engagement data using Python.

The analysis combines **data cleaning, transformation, statistical analysis, exploratory data analysis, visualization, and business intelligence** to understand how content type, category, user demographics, devices, posting time, verification status, and sentiment influence social media engagement.

The project demonstrates how raw engagement data can be transformed into meaningful insights that can support **content strategy, audience targeting, engagement optimization, and data-driven decision-making**.

---

## Author

**Sabana Asmi R**

**Data Analyst Intern | Data Analytics Enthusiast**

### Skills

`Python` `SQL` `Power BI` `Excel` `Pandas` `NumPy` `Matplotlib` `Seaborn` `Plotly` `Data Analysis`



