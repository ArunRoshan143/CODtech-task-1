
 NAME : ARUN ROSHAN R S P
DOMAIN NAME    : DATA ANALYST
INTERN ID      :
BATCH DURATION : 4 WEEKS
MENTOR NAME    : Sravani gouni

IPL Ball-by-Ball Data Analysis
This project provides a comprehensive analysis of the IPL Ball-by-Ball data from 2008 to 2024. Using Python and its data visualization libraries, we explore various aspects of the game, including the distribution of runs, types of wickets, and key players involved in dismissals.

Getting Started
Prerequisites
Ensure you have the following libraries installed:

pandas
matplotlib
seaborn
google.colab (if you are using Google Colab)
Installation
You can install the required libraries using pip:

Usage
Upload the Data:

If you are using Google Colab, you can upload the dataset using the following code:

from google.colab import files
uploaded = files.upload()
file_name = 'IPL_BallByBall2008_2024(Updated).csv'
ipl_data = pd.read_csv(file_name)
Preprocess the Data:

The data requires some preprocessing steps, such as converting dates to datetime format and filling missing values:

ipl_data['Date'] = pd.to_datetime(ipl_data['Date'], errors='coerce')
ipl_data['Ball No'] = ipl_data['Ball No'].astype('int', errors='ignore')
ipl_data['type of extras'].fillna('none', inplace=True)
ipl_data['wicket_type'].fillna('no wicket', inplace=True)
ipl_data['Player Out'].fillna('no wicket', inplace=True)
ipl_data['fielders_involved'].fillna('none', inplace=True)
Data Visualization:

The project includes several visualizations to explore the data:

Distribution of Runs Scored per Ball:

sns.set(style='whitegrid')
plt.figure(figsize=(10, 6))
sns.histplot(ipl_data['runs_scored'], bins=15, kde=True)
plt.title('Distribution of Runs Scored per Ball')
plt.xlabel('Runs Scored')
plt.ylabel('Frequency')
plt.show()
Count of Wickets by Type:

plt.figure(figsize=(12, 6))
wicket_counts = ipl_data['wicket_type'].value_counts().drop('no wicket')
sns.barplot(x=wicket_counts.index, y=wicket_counts.values)
plt.title('Count of Wickets by Type')
plt.xlabel('Wicket Type')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.show()
Top 10 Players Involved in Dismissals:

plt.figure(figsize=(12, 6))
top_fielders = ipl_data['fielders_involved'].value_counts().drop('none').head(10)
sns.barplot(x=top_fielders.index, y=top_fielders.values)
plt.title('Top 10 Players Involved in Dismissals')
plt.xlabel('Player')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.show()
Correlation Heatmap of Numerical Features:

plt.figure(figsize=(10, 8))
numerical_features = ipl_data[['Innings No', 'Ball No', 'runs_scored', 'extras', 'score']]
correlation_matrix = numerical_features.corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', linewidths=0.5)
plt.title('Correlation Heatmap of Numerical Features')
plt.show()
Conclusion
This project demonstrates the use of Python for analyzing and visualizing sports data. By following the steps above, you can replicate the analysis and gain insights into IPL matches from 2008 to 2024.

Acknowledgments
The IPL dataset was provided for educational purposes.
Thanks to the contributors of the libraries used in this project.
Output:
Histogram:
![im1](https://github.com/ArunRoshan143/EDA-intern/assets/122539338/e894eeac-e5f9-4b78-8d04-0cb818c6eace)

Barchart:
![im2](https://github.com/ArunRoshan143/EDA-intern/assets/122539338/a3d12459-b99d-457d-a9a4-a7e1b4cece1f)

Heatmap:
![im3](https://github.com/ArunRoshan143/EDA-intern/assets/122539338/9e44a58e-ee12-450b-9026-954203963775)
