# Ex-04-Multivariate-Analysis

### AIM:

To perform Multivariate EDA on the given data set.

### EXPLANATION:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

### ALGORITHM:

### STEP 1

Import the built libraries required to perform EDA and outlier removal.

### STEP 2

Read the given csv file.

### STEP 3

Convert the file into a dataframe and get information of the data.

### STEP 4

Return the objects containing counts of unique values using (value_counts()).

### STEP 5

Plot the counts in the form of Histogram or Bar Graph.

### STEP 6

Use seaborn the bar graph comparison of data can be viewed.

### STEP 7

Find the pairwise correlation of all columns in the dataframe.corr() .

### STEP 8

Save the final data set into the file.

### PROGRAM:
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```
### OUTPUT:

### DATASET

![image](https://user-images.githubusercontent.com/120443233/230724329-35faf7bd-41f8-4640-b9cb-bf1cdae14956.png)

### HEAD()

![image](https://user-images.githubusercontent.com/120443233/230724345-02b934d7-9327-4725-b9fc-75bd3d578005.png)

### INFO()

![image](https://user-images.githubusercontent.com/120443233/230724372-14313d2a-cb1f-49d7-ad01-1c4bda75487e.png)

### DESCRIBE()

![image](https://user-images.githubusercontent.com/120443233/230724407-9120fab0-eb57-40b4-9248-25db802bbde6.png)

### DATATYPE()

![image](https://user-images.githubusercontent.com/120443233/230724431-8adbf44b-206a-41d8-9eff-19b21266db8e.png)

### ISNULL

![image](https://user-images.githubusercontent.com/120443233/230724443-1db796ac-7d94-40a7-9688-25871670a780.png)

### Postal code has outliers.

![image](https://user-images.githubusercontent.com/120443233/230724476-996c3479-5259-431a-b129-623c28cd83a7.png)

### After removing outliers from Postal Code.

### MULTIVARIATE ANALYSIS

### SCATTER PLOT

![image](https://user-images.githubusercontent.com/120443233/230724531-92a0cf0b-81a5-46f0-aece-8a8eb6551c63.png)

### BARPLOT

![image](https://user-images.githubusercontent.com/120443233/230724560-a6ff43fd-764e-4abe-a106-b1fa629668fa.png)

### West has more sales than other region.

![image](https://user-images.githubusercontent.com/120443233/230724604-8ce4e24c-d2ee-45f3-b4bd-f92bd7f593e8.png)

California has more sales than other states.

### SEGMENTATION

![image](https://user-images.githubusercontent.com/120443233/230724633-d9a1c8d6-326b-42b9-9807-2d3279dad329.png)

Technology has more sales than other category.

### SUBPLOTS

![image](https://user-images.githubusercontent.com/120443233/230724676-86124dd2-dd60-439b-b825-3086f29ec4cc.png)

### CORRESSION

![image](https://user-images.githubusercontent.com/120443233/230724712-dd656846-fbd8-4ee7-8b93-78914078c0ab.png)

### HEATMAP()

![image](https://user-images.githubusercontent.com/120443233/230724737-3c536b46-1e47-408e-b4db-7a97a78514f4.png)

### RESULT

Hence The Performance of the Multivariate EDA on the given data set is verified.
