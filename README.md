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


# CODE AND OUTPUT
NAME : SACHIN.C
REG NO. : 212222230125

```PYTHON
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
print(df)
```
![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/aefc7c1e-efd3-45a6-815c-e287bee7f043)

### df.isnull.sum()

![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/b676b7b9-016d-4bf8-ae10-3add88fba1d9)

```PYTHON
plt.figure(figsize=(5,5))
plt.title("data with outliners")
df.boxplot()
plt.show()
```
![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/4b2c05af-3dce-468d-a8dd-59d355215f50)

```PYTHON
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
![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/e6e07657-064c-4a5f-b61d-530356516a21)

```PYTHON
sns.barplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="center")
plt.title("highest total bill amount by day of the week")
```

![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/b45c792b-f3b1-42e0-b14f-093314be16d7)

```PYTHON
sns.boxplot(x=df["smoker"],y=df["tip"],hue=df["smoker"])
plt.title("average tip amount given by smokers and non-smokers")
```

![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/96541882-8184-4de2-8c44-b2b7e9e3af5b)

```PYTHON
df["tip_percent"]=df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'], y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
```
![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/4085d4bc-241e-4973-9813-bc29626a392f)

```python
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()
```
![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/47919b29-5e6e-4308-8a4d-98083c7b19a3)

```python
sns.barplot(x=df["size"],y=df["total_bill"],hue=df["size"])
plt.title("average total bill amount by dinning party size")
```

![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/4bd6acc6-8e1a-409f-8d3c-2d49ca2e8cf1)

```python
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```

![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/b1c6df4a-22d5-4fed-9388-b84e2132260d)

```python
sns.violinplot(x="time",y="tip",data=df)
plt.title("tip amount time of day")
```

![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/7cab0f15-e453-4c2d-bd9c-f2c5519d3ce0)

```python
sns.scatterplot(x="total_bill",y="tip",data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```

![image](https://github.com/Sachin-vlr/ODD2023-Datascience-Ex-09/assets/113497666/b7f0e4ab-e0df-4632-92b3-bd1730ea87fb)

# RESULT:
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.





