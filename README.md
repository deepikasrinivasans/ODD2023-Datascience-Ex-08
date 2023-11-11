# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

## CODE
### inserting libraries
```
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt
df=pd.read_csv("/content/Superstore - Superstore.csv (1).csv")
df.head()
df.info()
df.isnull().sum()
```
###  Data Visualization using seaborn
#### lineplot
```
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

sns.lineplot(x='Ship Mode', y='Category',hue="Segment",data=df)
plt.title("Multiline Plot")
plt.show()
```
#### barplot
```
sns.barplot(x="Category",y="Sales",data=df)

sns.barplot(x='Region', y='Sales', data=df,palette='Set1')
plt.title("Sales in different Regions")
plt.show()
```
#### scatterplot
```
sns.scatterplot(x='Category',y='Sub-Category',data=df)
plt.title("Scatterplot")
plt.show()

sns.scatterplot(x='Category',y='Sub-Category',hue='Segment',data=df)
plt.show()
```
#### boxplot
```
sns.boxplot(x="Sub-Category",y="Discount",data=df)
plt.xticks(rotation=90)

sns.boxplot( x="Profit", y="Category",data=df)
```
#### pointplot
```
sns.pointplot(x=df["Quantity"],y=df["Discount"])
```
#### violinplot
```
sns.violinplot(x="Profit",data=df)
```
#### countplot
```
sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)
plt.xticks(rotation=90)
 ```
#### histogram
```
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
```
#### KDEplot
```
sns.kdeplot(x="Discount", data = df,hue='Category')
```
### Data Visualization using Matplotlib
#### plot
```
plt.plot(df['Region'], df['Sales'])
plt.show()
```
#### Heatmap
```
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
#### piechart
```
df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()
```
#### Histogram
```
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="black",bins=10)
plt.xticks(rotation =90)
plt.show()
```
#### barplot
```
plt.bar(df['Category'],df.index)
plt.show()
```
#### scatterplot
```
plt.scatter(df["Region"],df["Profit"], c ="red")
plt.show() 
```
#### boxplot
```
plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUTPUT

#### Initial data:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/8a6cd603-a006-48ae-a544-bbe01b360f54)

#### Data information:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/c69ce3ba-902a-41f4-93e8-43d06b05f4b5)

#### Null values:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/ec68324f-b907-4c59-a7ed-98ee54dec44b)

### Data visualization using Seaborn

#### Lineplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/a5079f5b-e1a2-429a-9a17-117d41da277f)

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/d01edbed-cce5-4beb-93d2-32b936ea2151)


#### Barchart:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/24050a1d-8d2a-4168-ab1d-329b69418227)

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/1dba40a6-8630-49fa-9760-e72870c1b364)

#### Scatterplot:

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/2d7a2798-6857-4aa0-8206-14559a03851b)


![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/2baa7ff8-a63d-49b3-b21b-233da9afbffe)

#### Boxplot:

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/928a9078-6c77-492d-b8c6-b32230d1678f)


![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/ba57c273-1345-4a6c-ba59-d2fa1ee0759f)


#### Pointplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/efbda28e-f061-4ab8-90e9-eb327c921a19)


#### Violinplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/3e65819f-7dfe-49e4-9fb7-938c16d54c2b)


#### Countplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/7b772059-76a0-4b80-b876-572fce0ccdc0)

#### Histogram:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/ff929223-c6ee-42fd-86da-2342f2d32883)

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/472f45bd-401f-4258-8d3f-899d72500355)

#### KDEplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/f9c9264f-73b2-4557-9378-bc1729a06dcf)


### Data visualization using Matplot

#### Plot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/862d50e8-90d3-457d-bcc5-9dbebc9a3413)


#### Heatmap:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/93948726-d681-49b5-85f7-a161fd56ba06)

#### Piechart:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/01b43bc5-f60a-44f3-a2ec-573590318cab)


![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/29645ce1-09dc-4864-8f46-cbc48c3adfdb)


#### Histogram:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/2575ba1f-980d-403d-a3dc-3cd1917a32df)


#### Barplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/3a9ee75a-b70d-4be0-8fdf-535b850311c2)

#### Scatterplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/be654174-1235-40a0-8ccf-dd780e91d5af)


#### Boxplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/ad7fcedc-f1a9-4e18-a6b0-247d3fcb01dd)

## Result :
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
