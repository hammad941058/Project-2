Data Handling in Google Colab
Importing, cleaning, and Analyzing Datasets
Learn essential data handling techniques in Google Colab using pandas and numpy.
Understand the process of data preprocessing and analysis.
Importing Libraries,pandas: Data manipulation and analysis tools.
Numpy: Support for large, multi-dimensional arrays and matrices.
Mounting Google Drive, Mounting Google Drive to access files stored in Google Colab environment.
Uploading and Inspecting Dataset1, Loading dataset1 from Google Drive Displaying the first five rows using dataset1.head()
Boxplot of Dataset1, Visualizing the distribution of data in dataset1 using a boxplot.
Further analysis of Dataset1, Checking  last five rows, dataset info, data types, index, null values, description, and unique values in dataset1.
Data Cleaning in dataset1, Droping the ‘hr’ column from dataset1.
Calculating Null percentage in Dataset1, Calculating the percentage of null values in dataset1.
Dataset1 Overview, Displaying the shape of dataset (number of rows and columns)
Uploading and inspecting Dataset2, Loading dataset2 from Google Drive Displaying the first five rows using dataset2.head()
Further analysis of Dataset2, Checking the last five rows, dataset info, null values, and description of dataset2.
Data Cleaning in Dataset2, Replacing null values with mean and droping  ‘Unnamed: 0’ column from dataset2.
Merging Datasets, Merging dataset1 and dataset2 based on a common column.
Null percentage after merging datasets, Calculating the percentage of null values in bike_count.
Uploading and inspecting dataset3, Loading dataset3 from Google Drive Displaying the first five rows using dataset3.head()
Further Analysis of Dataset3, Checking last five rows,dataset info, null values, and description of dataset3.
Concatenating Datasets, This slide concatenates dataset3 and another dataset bike_count to create a larger dataset and displays the first five rows of the combined dataset.
Final Data Overview, Provide an overview of the final dataset after concatenation.
Codes: df4.head(),df4.isnull(),df4.tail(),df4.describe(),df4.info(),df4.shape,df4.dtypes,df4.index,df4.isnull().sum()/df4.shape[0]*100
Here, we summarize the final concatenated dataset by checking for null values, displaying its last five rows, providing descriptive statistics, and detailing its shape and data types.
Statistical Analysis, Objective: Perform statistical analysis on the final dataset.
Codes:
	 df4['instant'].mean()
df4['hr'].mean()
df4['temp'].mean()
df4['holiday'].mode()
df4['atemp'].median()
upper_limit=df4['temp'].mean()+3*df4['temp'].std()
lower_limit=df4['temp'].mean()-3*df4['temp'].std()
upper_limit
lower_limit
df4.loc[df4['temp']>upper_limit]
df4.loc[df4['temp']<lower_limit]
outliers=df4.loc[(df4['temp']>upper_limit)|(df4['temp']<lower_limit)]
q3=df4['temp'].quantile(0.75)
q1=df4['temp'].quantile(0.25)
iqr=q3-q1
iqr
zscore=(df4['temp']-df4['temp'].mean())/df4['temp'].std()
zscore
filtered_data=df4[(zscore<3)]
skewness=stats.skew(df4['temp'])
Explanation:
		This slide performs a comprehensive statistical analysis on the final dataset, including mean, median,mode, upper limit, and lowe limits, interquartile range, z-score calculation, outlier removal, and skewness of the ‘temp’ column.
