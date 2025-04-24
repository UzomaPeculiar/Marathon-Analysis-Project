# Marathon-Analysis-Project

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Sources](#data-sources)
3. [Tools Used](#tools-used)
4. [Data Cleaning/Preparation](#data-cleaningpreparation)
5. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
6. [Data Analysis](#data-analysis)
7. [Results/Findings](#resultsfindings)
8. [Recommendations](#recommendations)
9. [Limitations](#limitations)
10. [References](#references)

## Project Overview
This project provides an in-depth analysis of YouTube streamers to uncover insights into performance metrics, audience distribution, content trends, brand collaborations, and potential recommendation strategies. By leveraging statistical and visual analysis, the goal is to understand the characteristics that define top-performing streamers and inform better content recommendation systems for platform users and marketers.

![download](https://github.com/user-attachments/assets/b4c81001-30a3-494c-b9e8-25ad4b088211)


## Data Sources
The dataset used in this project, `youtubers_df.csv`, includes detailed information on YouTube streamers, such as:
- Number of subscribers, visits, likes, and comments
- Content categories
- Audience country distribution
- Brand collaborations

## Tools Used
The project leverages a range of modern data analysis and visualization tools, including:
- **Programming Language**: Python 3 [https://www.python.org]
- **Libraries**:
  - `pandas` – data manipulation
  - `numpy` – numerical operations
  - `matplotlib` and `seaborn` – data visualization
- **Environment**: Jupyter Notebook [https://www.anaconda.com/products/distribution]

## Data Cleaning/Preparation
Key cleaning steps included:
- Checked for and handled missing values using `isnull()` and visualized with heatmaps.
- Identified outliers using boxplots for metrics such as `subscribers`, `likes`, and `visits`.
- Renamed and standardized column headers for consistency.
- Created new features such as a composite engagement score and textual content for recommendation modeling.

## Exploratory Data Analysis (EDA)
The EDA focused on answering the following questions:
- What are the most common content categories among top YouTubers?
- Is there a relationship between subscribers and other metrics like likes or comments?
- Which countries have the most engaged audiences?
- Are certain content types preferred in different regions?
- How do performance metrics distribute across different streamer segments?

Visual tools such as bar charts, histograms, and correlation heatmaps were used to reveal trends and patterns.

## Data Analysis
### **Key Code and Features:**
- **Correlation Analysis**: Revealed strong positive relationships between subscribers, likes, and comments.
- **Audience Segmentation**: Grouped data by `audience_country` to understand regional content preferences.
- **Brand Collaborations**: Assessed relationship between high-performing streamers and frequency of brand deals.

### **Sample Code Snippet – Correlation Heatmap**
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Select numerical performance metrics
metrics = ['subscribers', 'likes', 'comments', 'visits']
correlation_matrix = df[metrics].corr()

# Plot heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt=".2f")
plt.title('Correlation Heatmap of Performance Metrics')
plt.show()
```

## Results/Findings
The analysis yielded several significant insights:
- Streamers with higher engagement metrics can have noticeably more brand collaborations.
- A significant number of high-performing streamers belonged to a small subset of categories.
- The content-based recommendation model successfully identified similar streamers by category and engagement profile.
- Entertainment and Gaming were one of the most represented content categories among streamers.

## Recommendations
Based on the analysis, the following recommendations are proposed:
- **Content Strategy:** Aspiring streamers should focus on high-engagement categories such as Entertainment, Education, or Gaming.
- **Regional Focus:** YouTube could promote regionally popular categories to boost local engagement.
- **Platform Optimization:** Use hybrid recommendation systems to suggest content that blends user preferences with high-performing streamer profiles.
- **Brand Engagement:** Brands should target influencers with both high engagement and sustained growth rather than only high subscriber counts.
- **Data-Driven Adjustments:** Continuously monitor performance metrics and adjust strategies accordingly to maintain and enhance audience retention.

## Limitations
While the analysis provides valuable insights, it is important to note the following limitations:
- **Temporal Dimension:** The dataset appears static; trends over time could not be analyzed.
- **Collaborations:** Some brand-related data may be incomplete or unavailable, affecting the robustness of marketing analysis.
- **Temporal Relevance:** Trends identified may shift over time; hence, continuous monitoring is recommended.
- **Lack of Demographics:**  Limited audience segmentation due to the absence of age, gender, or device usage data.

## References
- YouTube Data API Documentation – for guidelines on data collection and usage.
- Python Data Science Handbook by Jake VanderPlas – for techniques in data cleaning and analysis.
- Official documentation for Pandas, NumPy, Matplotlib, and Seaborn – [https://pandas.pydata.org] [https://numpy.org] [https://matplotlib.org] [https://seaborn.pydata.org]
