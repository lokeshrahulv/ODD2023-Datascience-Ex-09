# Ex-09-Data-Visualization-

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

## CODE AND OUTPUT:

Name: LOKESH RAHUL V V
Reg no:212222100024

```python 
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
print(df)
```
<img width="230" alt="1" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/24b2f93e-ec2d-4c98-aa8d-3a63a6bbd694">

```python
df.isnull().sum()
```
<img width="74" alt="2" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/246cc668-20f6-4bf0-a424-12b3549eacfc">

```python
plt.figure(figsize=(5,5))
plt.title("data with outliners")
df.boxplot()
plt.show()
```
<img width="218" alt="3" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/bd83a021-d237-49d7-8283-cba2b7339e73">

```python
plt.figure(figsize=(5,5)) 
cols=["size","tip","total_bill"]
q1=df[cols].quantile(0.25)
q3=df[cols].quantile(0.75)
iqr=q3-q1
df=df[~((df[cols]<(q1-1.5*iqr))|(df[cols]>(q3+1.5*iqr))).any(axis=1)]
plt.title("dataset after removing outliners")
df.boxplot()
plt.show()
```
<img width="218" alt="4" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/3060b898-67e3-4772-90e0-694ae365f52e">

```python
sns.barplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="center")
plt.title("highest total bill amount by day of the week")
```
<img width="283" alt="5" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/62104b3a-3999-4f5f-af86-1827950c129a">

```python
sns.boxplot(x=df["smoker"],y=df["tip"],hue=df["smoker"])
plt.title("average tip amount given by smokers and non-smokers")
```

<img width="280" alt="6" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/74248525-a2ef-4551-902d-3cb7ebd061d3">

```python
df["tip_percent"]=df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'], y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
```

<img width="289" alt="7" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/4c4091d2-d716-4f26-9b29-737d715f741a">

```python
sns.boxplot(x=df["sex"],y=df["tip"],hue=df["sex"])
plt.title("tips based on gender")
```

<img width="279" alt="8" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/1580de63-212e-4dd1-8a24-6387246d9560">

```python
sns.scatterplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="best")
plt.title("total bill amount by day of te week")
```

<img width="293" alt="9" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/d4a845d2-e019-444e-b4c9-74149b93405a">

```python
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()
```

<img width="293" alt="10" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/db3fed15-d3ed-4bf0-b1a8-5a0971b679f5">

```python
sns.barplot(x=df["size"],y=df["total_bill"],hue=df["size"])
plt.title("average total bill amount by dinning party size")
```
<img width="286" alt="11" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/19f0e4e3-581d-4460-89af-b7ca2d233664">

```python
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```
<img width="278" alt="12" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/150798eb-4d77-49c7-aad6-03870898714a">

```python
sns.violinplot(x="time",y="tip",data=df)
plt.title("tip amount time of day")
```
<img width="284" alt="13" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/2f944b46-5f8a-4bc3-af6e-7d2c775c616d">

```python
sns.scatterplot(x="total_bill",y="tip",data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```
<img width="280" alt="14" src="https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-09/assets/118423842/6ff4d745-be08-422e-ac1f-275881e0d7fe">

## RESULT:
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.

