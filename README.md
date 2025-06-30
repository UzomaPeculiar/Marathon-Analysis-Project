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
This project provides an in-depth analysis of ultramarathon race data to uncover insights into athlete performance, age distribution, and race popularity. The dataset focuses on 50km and 50mi races held in the USA in 2020. By leveraging data cleaning, statistical analysis, and visualization techniques, the goal is to understand the characteristics of ultramarathon participants and race events, providing insights for race organizers, athletes, and researchers.




## Data Sources
The dataset used in this project, TWO_CENTURIES_OF_UM_RACES.csv, includes detailed information on ultramarathon races, such as:

- Event details (name, date, distance, number of finishers)
- Athlete performance metrics (finish time, average speed)
- Athlete demographics (age, gender, ID)

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

- Filtered the dataset to include only 50km and 50mi races in the USA in 2020.
- Cleaned Event name by removing country codes (e.g., "Race Name (USA)" → "Race Name").
- Calculated athlete_age by subtracting Athlete year of birth from 2020.
- Cleaned Athlete performance by removing the "h" suffix from time values (e.g., "5:30:00 h" → "5:30:00").
- Converted Athlete performance to seconds (performance_seconds) for numerical analysis.
- Dropped unnecessary columns (Athlete club, Athlete country, Athlete year of birth, Athlete age category).
- Handled missing values by dropping rows with null athlete_age or invalid performance_seconds.
- Checked for and confirmed no duplicate rows.
- Standardized data types (athlete_age to int, avg_speed to float).
- Renamed columns for clarity (e.g., Event name → event_name, Athlete performance → performance_time).
- Created a new feature, age_group, by binning athlete_age into categories for analysis.

## Exploratory Data Analysis (EDA)
The EDA focused on answering the following questions:

- What is the age distribution of athletes by gender?
- How do performance times vary across race distances (50km vs. 50mi) and genders?
- How does average speed differ across age groups and race distances?
- Which races attract the most participants?
- Are there correlations between age, average speed, and performance time?

Visual tools such as histograms, box plots, bar charts, and correlation heatmaps were used to reveal trends and patterns.

## Data Analysis
### **Key Code and Features:**

- **Summary Statistics:** Generated descriptive statistics for athlete_age, avg_speed, performance_seconds, and num_finishers.
- **Age Distribution:** Visualized the distribution of athlete ages by gender using a histogram with KDE.
- **Performance Analysis:** Compared performance times across distances and genders using box plots.
- **Speed by Age Group:** Analyzed average speed by age group and distance using box plots.
- **Race Popularity:** Identified the top 10 races by number of finishers using a bar plot.
- **Correlation Analysis:** Computed correlations between athlete_age, avg_speed, and performance_seconds.

### **Sample Code Snippet – Correlation Heatmap**
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Select numerical performance metrics
metrics = ['athlete_age', 'avg_speed', 'performance_seconds']
correlation_matrix = df2[metrics].corr()

# Plot heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt=".2f")
plt.title('Correlation Matrix (Age, Speed, Performance Time)')
plt.show()
```

## Results/Findings
The analysis yielded several significant insights:

- **Age Distribution:** Athletes span a wide age range, with distinct patterns by gender, indicating diverse participation in ultramarathons.
- **Performance by Distance:** 50mi races generally have longer performance times than 50km races, with potential gender-based differences in variability.
- **Speed by Age Group:** Certain age groups (e.g., 30-40) may exhibit higher average speeds, varying by race distance.
- **Popular Races:** A small subset of races attracts significantly more participants, indicating high popularity.
- **Correlations:** There is a notable correlation between age, average speed, and performance time, suggesting younger athletes may perform faster in some contexts.

## Recommendations
Based on the analysis, the following recommendations are proposed:

- **Race Organizers:** Focus on promoting popular races to attract more participants and optimize event logistics based on participant demographics.
- **Athlete Training:** Tailor training programs to age groups and race distances, leveraging insights on speed and performance trends.
- **Event Planning:** Use participation trends to schedule races during peak interest periods and in high-demand regions.
- **Data-Driven Strategies:** Continuously monitor performance metrics to identify emerging trends and adjust race formats or marketing strategies.
- **Research Opportunities:** Use the cleaned dataset for further studies, such as predicting performance based on age and gender.

## Limitations
While the analysis provides valuable insights, it is important to note the following limitations:

- **Temporal Scope:** The dataset is limited to 2020, preventing analysis of trends over time.
- **Geographic Scope:** The analysis focuses only on USA races, limiting generalizability to other regions.
- **Data Completeness:** Missing or invalid performance times were dropped, potentially excluding some athletes.
- **Demographic Data:** Limited demographic information (e.g., no detailed athlete background) restricts deeper segmentation.
- **Static Analysis:** Trends identified may shift in future years, requiring ongoing data collection.

## References
- Python Data Science Handbook by Jake VanderPlas – for techniques in data cleaning and analysis.
- Official documentation for Pandas, NumPy, Matplotlib, and Seaborn – [https://pandas.pydata.org] [https://numpy.org] [https://matplotlib.org] [https://seaborn.pydata.org]
- Dataset: TWO_CENTURIES_OF_UM_RACES.csv [https://kaggle.com].
