# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
~~~
# Importing packages
import pandas as pd
import numpy as np
import seaborn as sns
from matplotlib import pyplot as plt
# Reading dataset
df=pd.read_csv("Superstore.csv",encoding=('ISO-8859-1'))
df.head() 
#Data Visualization using Seaborn
#1.Line plot
plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
#2.Scatterplot
sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)
#3.Boxplot
sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)
#4.Barplot
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)
#5.Pointplot
sns.pointplot(x=df["Quantity"],y=df["Discount"])
#6.Count plot
sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df) 
#7.Histogram
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
#8.KDE Plot
sns.kdeplot(x="Profit", data = df,hue='Category')
#Data Visualization Using MatPlotlib
#1.Plot
plt.plot(df['Category'], df['Sales'])
plt.show()
#2.Heatmap
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
#3.Piechart
df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()
#4.Histogram
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()
#5.Bargraph
plt.bar(df.index,df['Category'])
plt.show()
#6.Scatterplot
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()
#7.Boxplot
plt.boxplot(x="Sales",data=df)
plt.show()
~~~
# OUPUT
# Reading data
![op1 (1)](https://user-images.githubusercontent.com/95342910/172289372-5ae9f3ef-9294-4b7d-8a3a-83881e285a99.png)

# Data Visualization using Seaborn
# lineplot
![op2](https://user-images.githubusercontent.com/95342910/172289639-1d884d80-47db-4338-b725-246d06314eaa.png)

![op3](https://user-images.githubusercontent.com/95342910/172289689-fc8ff0dc-d597-418a-a715-221b1af5771a.png)

# scatterplot
![op4](https://user-images.githubusercontent.com/95342910/172289829-b88cb2fe-58dc-4e48-a685-ccd4562e3d28.png)

![op5](https://user-images.githubusercontent.com/95342910/172289849-5da49952-5f48-4372-9150-72df389106e6.png)

![op6](https://user-images.githubusercontent.com/95342910/172289908-5dc6ce9f-f487-49a0-8e83-26277816c752.png)

# boxplot
![op7](https://user-images.githubusercontent.com/95342910/172289967-a8922dd9-32f3-48b5-8054-20cc243a7b82.png)

![op8](https://user-images.githubusercontent.com/95342910/172289980-73beb0b4-7907-43c0-883d-f2fc4b02f426.png)

# barplot
![op9](https://user-images.githubusercontent.com/95342910/172290237-d5ee73a8-64b6-4b20-bd69-d3f78517e53b.png)

![op10](https://user-images.githubusercontent.com/95342910/172290254-006c907f-f12a-408b-b236-ea54d86cc14f.png)

# pointplot
![op11](https://user-images.githubusercontent.com/95342910/172290303-4462e6e4-44e3-427a-881d-807c1bb786ef.png)

# countplot
![op12](https://user-images.githubusercontent.com/95342910/172290443-6f971744-7bb5-4dea-a788-97789e698591.png)

![op13](https://user-images.githubusercontent.com/95342910/172290470-77b9964a-56f6-4c29-b8cf-7ecc2cb45c49.png)

# histogram
![op14](https://user-images.githubusercontent.com/95342910/172290520-03217c60-7958-4c1a-8c42-900b4e583410.png)

# KDE plot
![op15](https://user-images.githubusercontent.com/95342910/172290582-01285b96-8813-49a0-ba65-26c3e54df784.png)

# Data Visualization Using MatPlotlib
# plot
![op16](https://user-images.githubusercontent.com/95342910/172290682-17e0b693-42d2-4f9c-9273-7fd5eb27f1f1.png)

# heatmap
![op17](https://user-images.githubusercontent.com/95342910/172290768-a429d7c9-39c5-4980-ba4c-bb73150374c4.png)

# piechart
![op18](https://user-images.githubusercontent.com/95342910/172290830-e1890521-8424-4fd8-91ba-4f2aeb532a5b.png)

# histogram
![op19](https://user-images.githubusercontent.com/95342910/172290908-a3c063f6-1545-4e54-b112-ec36ac5f59ef.png)

# bargraph
![op20](https://user-images.githubusercontent.com/95342910/172290979-a901e3df-6963-46ee-a83e-6056733b0e17.png)

# scatterplot
![op21](https://user-images.githubusercontent.com/95342910/172291018-a6e3dad3-b74b-44f6-9ac6-f0734c8073bd.png)

# boxplot
![op22](https://user-images.githubusercontent.com/95342910/172291087-e10a54b6-ca7e-4828-a756-142a41d5a7e4.png)

## RESULT
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
