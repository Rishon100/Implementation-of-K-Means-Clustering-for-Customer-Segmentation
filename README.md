# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: V RISHON ANAND
RegisterNumber: 24900460 
*/
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i, init = "k-means++")
  kmeans.fit(data.iloc[:, 3:])
  wcss.append(kmeans.inertia_)
  
plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c = "red", label = "cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c = "black", label = "cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c = "blue", label = "cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c = "green", label = "cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c = "magenta", label = "cluster4")
plt.legend()
plt.title("Customer Segments")
## Output:
![K Means Clustering for Customer Segmentation](sam.png)
![Screenshot 2024-12-18 223840](https://github.com/user-attachments/assets/e7f73812-7c6a-403b-8680-b0a17f869079)
![Screenshot 2024-12-18 223854](https://github.com/user-attachments/assets/3d5c2458-e342-47e1-82f2-46d5eb1d361d)
![Screenshot 2024-12-18 223902](https://github.com/user-attachments/assets/a1167f12-55df-4694-abad-49a00faeabea)
![Screenshot 2024-12-18 223923](https://github.com/user-attachments/assets/0f9b7ab0-0f05-4df0-8f1b-d1b32639bd2d)
![Screenshot 2024-12-18 223929](https://github.com/user-attachments/assets/4a312a5d-5a4a-42dd-a724-313e2142453c)
![Screenshot 2024-12-18 223940](https://github.com/user-attachments/assets/139f2216-a36d-4148-bbbe-c137c580783a)
![Screenshot 2024-12-18 223948](https://github.com/user-attachments/assets/9d7956cd-b33c-46b8-b7f0-e7f7516d40b7)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
