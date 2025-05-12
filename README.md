# NAME : Bala B 
# REG NO : 212224100005
# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
~~~python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
~~~
![image](https://github.com/user-attachments/assets/6a8b982b-37bc-47a1-98fe-f26571604350)
~~~python
df = sns.load_dataset("tips")
df
~~~
![image](https://github.com/user-attachments/assets/5c9ac016-30ab-423a-82be-f85705a82683)
~~~python
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
~~~
![image](https://github.com/user-attachments/assets/173c8a99-a241-412e-98d0-31eed6395dc2)
~~~python
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]

sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
~~~
![image](https://github.com/user-attachments/assets/7bb2038b-19f0-4044-b857-3322dfd21bcc)
~~~python
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
~~~
![image](https://github.com/user-attachments/assets/7ee75be1-03d6-4bec-bf79-812850594509)
~~~python
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
~~~
![image](https://github.com/user-attachments/assets/da03a5ed-1475-4a7d-8a56-daf135ce4024)
~~~python
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]

plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
~~~
![image](https://github.com/user-attachments/assets/f28fc8c4-423a-4d6f-9e3c-0bc4bb09a589)
~~~python
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
~~~
![image](https://github.com/user-attachments/assets/3e538484-cd55-47b9-8b87-e0b485dfcf3d)
~~~python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
mohan = pd.read_csv('/content/titanic_dataset (2).csv')
mohan
~~~
![image](https://github.com/user-attachments/assets/8ddd0d20-e3fc-48ee-bee5-fb72268d5155)
~~~python
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=mohan, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
~~~
![image](https://github.com/user-attachments/assets/3027b309-6771-4e0f-938d-52bcbe59a1af)
~~~python
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=mohan, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
~~~
![image](https://github.com/user-attachments/assets/7d6b1e28-c532-44fe-a3ab-af703b3f6989)
~~~python
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
~~~
![image](https://github.com/user-attachments/assets/86640486-0c4b-44c5-ad0f-f493c549f7c0)
~~~python
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
~~~
![image](https://github.com/user-attachments/assets/35e268fa-705f-4464-b404-591708caeb0b)
~~~python
sns.histplot(data = num_var, kde = True)
~~~
![image](https://github.com/user-attachments/assets/002a4b25-2fb1-4431-8462-f2b5eb7d31e7)
~~~python
df=pd.read_csv("/content/titanic_dataset (2).csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
~~~
![image](https://github.com/user-attachments/assets/34650281-2bbc-48ca-aad7-9900f54f2ec1)
~~~python
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
~~~
![image](https://github.com/user-attachments/assets/c477d173-7aeb-4341-a4eb-beb3e75fcb3b)
~~~python
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
~~~
![image](https://github.com/user-attachments/assets/fdeca82a-d659-4238-9c64-8a73e8047d30)
~~~python
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
~~~
![image](https://github.com/user-attachments/assets/c202c97b-34ef-4123-a515-9ca0ea331844)
~~~python
mart=pd.read_csv("/content/titanic_dataset (2).csv")
mart
~~~
![image](https://github.com/user-attachments/assets/5a78393f-4bbe-4ea7-a1e6-f82004f391f7)
~~~python
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
~~~
![image](https://github.com/user-attachments/assets/4b585435-2163-4b9e-9c8d-35e0adf055e0)
~~~python
sns.kdeplot(data=mart,x='PassengerId')
~~~
![image](https://github.com/user-attachments/assets/59d8c75d-1e91-45cc-b82c-e8250aa2d204)
~~~python
sns.kdeplot(data=mart,x='Age')
~~~
![image](https://github.com/user-attachments/assets/385f8cd0-a693-44f5-8850-7577c359e603)
~~~python
sns.kdeplot(data=mart)
~~~
![image](https://github.com/user-attachments/assets/b60b7348-1824-456f-8237-1a7cf8976e3c)
~~~python
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
~~~
![image](https://github.com/user-attachments/assets/41197af5-3d52-4ae7-90dc-a4c1db9d7c0a)
~~~python
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
~~~
![image](https://github.com/user-attachments/assets/98e70c54-cfcf-4e1b-925f-c398c09929c5)
~~~python
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
~~~
![image](https://github.com/user-attachments/assets/23f2a0f8-bfef-4adf-ab21-0af0ff8c4210)
~~~python
hm=sns.heatmap(data=data)
~~~
![image](https://github.com/user-attachments/assets/0243f3dd-2d2d-46a8-86c2-591648893cb1)

# Result:
 To perform Data Visualization using Seaborn python library for the given data is successful.
