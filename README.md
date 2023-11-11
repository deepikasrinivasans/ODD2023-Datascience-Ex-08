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
```
Developed by : Deepika S
RegisterNUmber : 212222230028
```
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
![d1](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/832a4d99-35ce-4b47-bd44-891d2319d4d7)

#### Data information:
![d2](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/6c66fc82-e438-4a81-8c5c-bb7df6ef1137)


#### Null values:
![d3](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/a01e96ae-abd4-403b-832d-92a1b646f4f0)


### Data visualization using Seaborn

#### Lineplot:

![d4](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/302b45b0-9578-4f51-a22d-3846e4922ae9)

![d5](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/24c6924a-d9c3-45b2-a3b0-8bc32f3a4512)


#### Barchart:
![d6](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/686fa92d-38c0-41eb-920d-0ba58fdb8e3a)

![d7](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/72c8fb0e-254a-4030-9774-6cdbf62f7b23)



#### Scatterplot:

![d8](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/27d6a4e4-d8cb-4b9a-9b2a-bf66091780e6)

![d9](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/1100dda4-6047-465b-9c5a-ed0cd11a38dc)



#### Boxplot:

![d10](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/d2808e40-7a4f-4aa3-8e5b-3e28b72048cc)


![d11](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/62b3bc24-8726-4b5b-801b-996184e9de44)



#### Pointplot:
![d12](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/f86a791f-e2c6-46cd-ac0b-775d8ae24c62)


#### Violinplot:
![d13](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/e7b68bea-4d96-42a6-aae8-93dc0c0fa7c5)


#### Countplot:
![d14](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/3d20efc0-7fc7-4fe0-98d1-84b16c7db44f)

#### Histogram:
![d15](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/dec7512b-f95b-44d3-bc19-96e896984b33)


![d16](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/c40dd80d-e2a0-4022-8292-c7e958393a0f)

#### KDEplot:
![d17](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/2fb04814-a0cd-4c2b-9d44-264e9d0886bd)

### Data visualization using Matplot

#### Plot:

![d18](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/3641b192-023e-4b30-b53e-dc3609243aa8)


#### Heatmap:
![d19](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/214b3801-c274-4c3c-a938-7b9042225489)


#### Piechart:
![d20](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/7f1ecd4e-0182-4d93-9589-1421094f3801)


![d21](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/f0f456f5-5a72-46ef-95b5-67e9ff4c65d4)


#### Histogram:
![d22](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/0584a7d8-c709-42c3-adfe-db32c0ba58bf)


#### Barplot:
![d23](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/c52a89c3-73b6-43cd-9132-fea7c163b588)


#### Scatterplot:

![d24](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-08/assets/119393935/de39b597-d3e6-4317-8a5e-a8194745d3ad)

#### Boxplot:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-08/assets/119393675/ad7fcedc-f1a9-4e18-a6b0-247d3fcb01dd)

## Result :
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
