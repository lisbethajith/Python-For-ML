# Exploratory Data Analysis (EDA) with Python

## Data Loading and Exploration:
- **Libraries**: Libraries like NumPy and pandas are fundamental for data manipulation and analysis in Python.
- **Data Loading**: The dataset "KMEANS_SAMPLE.csv" is loaded into a pandas DataFrame named `df_class` using the `read_csv()` function.
- **Exploration**: 
  - The `info()` method provides essential information about the DataFrame.
  - Checking for null values using `isnull().sum().sum()` helps identify missing data.
  - The shape of the DataFrame (`df_class.shape`) gives the number of rows and columns.

## Data Visualization:
- **Libraries**: Seaborn and matplotlib are widely used visualization libraries in Python.
- **Plots**:
  - Seaborn's `countplot` function creates bar plots showing the frequency of different categories within categorical variables.
  - Pie charts generated using matplotlib's `pie` function provide a visual representation of categorical proportions.
- **Subplots**: Subplots are created using matplotlib's `subplot` function to arrange multiple plots within a single figure.
- **Customizations**: Title modifications (`plt.title`), color adjustments (`color` parameter), and layout adjustments (`plt.tight_layout`) are applied to improve the clarity and visual appeal of the plots.

## Suggestions for Improvement or Additional Insights:
- **Statistical Summaries**: Compute mean, median, and standard deviation for numerical variables.
- **Advanced Visualization**: Explore techniques like scatter plots, pair plots, or heatmaps for deeper insights.
- **Statistical Analysis**: Employ statistical tests or machine learning algorithms for hypothesis testing or predictive modeling.
- **Advanced Visualization Libraries**: Consider libraries like Plotly or Bokeh for interactive visualizations.
- **Dimensionality Reduction**: Utilize techniques like PCA or clustering algorithms to uncover hidden structures.
- **Domain Knowledge**: Incorporate subject matter expertise for selecting relevant variables and interpreting results.

In summary, the provided code initiates an exploratory analysis of the dataset using Python's data manipulation and visualization libraries. Further leveraging advanced techniques and methodologies can unlock deeper insights and facilitate more informed decision-making from the data.



```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
%matplotlib inline
import warnings
warnings.filterwarnings('ignore')                                    
df_class=pd.read_csv("KMEANS_SAMPLE.csv")
df_class.head()
df_class.sample(5).style.set_properties(**{'background-color': 'blue',
                           'color': 'white',
                           'border-color': 'darkblack'})

df_class.info()
# checking for null
df_class.isnull().sum().sum()
# dimension

df_class.shape
## creating a percentage analysis of RP-wise distribution of data
round(df_class["gender"].value_counts(normalize=True)*100,2)

round(df_class["NationalITy"].value_counts(normalize=True)*100,2)
  ## creating a percentage analysis of RP-wise distribution of data
round(df_class["Semester"].value_counts(normalize=True)*100,2)
## creating a percentage analysis of RP-wise distribution of data
round(df_class["ParentAnsweringSurvey"].value_counts(normalize=True)*100,2)
  ## creating a percentage analysis of RP-wise distribution of data
round(df_class["StudentAbsenceDays"].value_counts(normalize=True)*100,2)
  ## creating a percentage analysis of RP-wise distribution of data
round(df_class["GradeID"].value_counts(normalize=True)*100,2)   

# Assuming df_class is your DataFrame containing gender information

plt.figure(figsize=(12, 6))

# Creating subplot 1
plt.subplot(1, 2, 1)
sns.countplot(x='gender', data=df_class)
plt.title("Gender Distribution", fontsize=20, color='Brown', pad=20)

# Creating subplot 2
plt.subplot(1, 2, 2)
df_class['gender'].value_counts().plot.pie(explode=[0.1, 0.1], autopct='%1.2f%%', shadow=True)
plt.title("Gender Distribution", fontsize=20, color='Brown', pad=20)

plt.tight_layout()
plt.show()



plt.figure(figsize=(12, 6))

# Creating subplot 1
plt.subplot(1, 2, 1)
sns.countplot(x='ParentAnsweringSurvey', data=df_class)
plt.title("ParentAnsweringSurvey Distribution", fontsize=20, color='Brown', pad=20)

# Creating subplot 2
plt.subplot(1, 2, 2)
df_class['ParentAnsweringSurvey'].value_counts().plot.pie(explode=[0.1, 0.1], autopct='%1.2f%%', shadow=True)
plt.title("ParentAnsweringSurvey", fontsize=20, color='Brown', pad=20)

plt.tight_layout()
plt.show()
plt.figure(figsize=(12, 6))

# Creating subplot 1
plt.subplot(1, 2, 1)
sns.countplot(x='StudentAbsenceDays', data=df_class)
plt.title("StudentAbsenceDays analysis", fontsize=20, color='Brown', pad=20)

# Creating subplot 2
plt.subplot(1, 2, 2)
df_class['StudentAbsenceDays'].value_counts().plot.pie(explode=[0.1, 0.1], autopct='%1.2f%%', shadow=True)
plt.title("StudentAbsenceDays", fontsize=20, color='Brown', pad=20)

plt.tight_layout()
plt.show()
```
