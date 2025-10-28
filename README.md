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
 ```
import seaborn as sns
import matplotlib.pyplot as plt

df=sns.load_dataset("tips")
df
```
<img width="534" height="438" alt="image" src="https://github.com/user-attachments/assets/3928501a-062d-4429-8007-36fc02f4331a" />

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto",palette="Set1")
```
<img width="785" height="574" alt="image" src="https://github.com/user-attachments/assets/f4cfd033-43b8-431e-a351-ee8b9fa93767" />

```
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
```
<img width="775" height="627" alt="image" src="https://github.com/user-attachments/assets/24d7e82d-6d36-4678-8f8c-05ad8dfb2019" />

```
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
```
<img width="751" height="616" alt="image" src="https://github.com/user-attachments/assets/ec47b370-2e64-4534-86cc-46dade4e03a4" />
```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
<img width="761" height="541" alt="image" src="https://github.com/user-attachments/assets/347d6cab-3f3a-4382-a42a-1942d26036a1" />

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
<img width="717" height="558" alt="image" src="https://github.com/user-attachments/assets/4ce6d3c4-cbbb-4265-880b-e6fea4c74cba" />

```
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set3')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
<img width="745" height="610" alt="image" src="https://github.com/user-attachments/assets/638b9f20-b27a-4d18-ac2c-71cb6ffc1caa" />

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=df,palette="Set1")
plt.xlabel('Total Bill')
plt.ylabel("Tip")
plt.title('Scatter Plot of Total Bill vs Tip Amount')
```
<img width="763" height="615" alt="image" src="https://github.com/user-attachments/assets/9d37119a-d27e-4149-a344-91008645d415" />

```
sns.histplot(data=df,x='total_bill', hue='smoker',kde=True,palette="Set2")
plt.xlabel('Total Bill')
plt.ylabel("Frequency")
plt.title('Distribution of Total Bill by Gender')
```
<img width="746" height="609" alt="image" src="https://github.com/user-attachments/assets/bbad909b-fafb-4761-9cd7-34bbc2241a69" />

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])
```
<img width="758" height="576" alt="image" src="https://github.com/user-attachments/assets/e9a0e8a1-e8e5-4a4d-86b9-3a72b637fa39" />

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])
```
<img width="732" height="580" alt="image" src="https://github.com/user-attachments/assets/9828bee6-1af9-43d4-9435-750786971f6f" />

```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,boxprops={"facecolor":"lightblue","edgecolor":"darkblue"},
            whiskerprops={"color":"black","linestyle":"--","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.5})
```
<img width="721" height="558" alt="image" src="https://github.com/user-attachments/assets/06830fa6-931a-4d87-8ca1-da9b22b41c7b" />

```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette="Set1",inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
<img width="732" height="607" alt="image" src="https://github.com/user-attachments/assets/56c4d7e1-59f9-4cbc-b039-8dc12fafacb2" />

```
import seaborn as sns
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip,palette="Set2")
```
<img width="727" height="578" alt="image" src="https://github.com/user-attachments/assets/76d2536c-2d3b-47b5-81cb-fa318cbbbc82" />

```
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"],palatte="Set1")
```
<img width="721" height="589" alt="image" src="https://github.com/user-attachments/assets/9b6baa3c-f7e8-455a-b2fe-78a709cc7a5b" />

```
import seaborn as sns
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='tip',y='day',data=tip,palette="Set2")
```
<img width="752" height="612" alt="image" src="https://github.com/user-attachments/assets/5db92273-92e5-44a0-aef3-02848021853b" />

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set3',alpha=0.8)
```
<img width="766" height="592" alt="image" src="https://github.com/user-attachments/assets/9b66b6dc-02f7-48b9-b3e5-4408892306ad" />

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set2',alpha=0.8)
```
<img width="747" height="588" alt="image" src="https://github.com/user-attachments/assets/e76e9de1-fa07-4f96-a48d-6fb2a15b522c" />

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set3',alpha=0.8)
```
<img width="754" height="607" alt="image" src="https://github.com/user-attachments/assets/541aa29b-6da8-4a6d-b65b-b6ffb33c6fcc" />

```
import seaborn as sns
tip =sns.load_dataset('tips')
num=tips.select_dtypes(include=['float64','int64']).columns
corr = tips[num].corr()
sns.heatmap(corr,annot=True,cmap="YlGnBu")
```
<img width="678" height="576" alt="image" src="https://github.com/user-attachments/assets/395966f9-5aac-4211-b107-76480776d4b5" />

```
sns.heatmap(corr,cmap="plasma")
```
<img width="675" height="594" alt="image" src="https://github.com/user-attachments/assets/88be10bf-7e46-4bad-b578-840934def8c0" />










# Result:
Data Visualization using seaborn python library for the given datas has been performed successfully.
