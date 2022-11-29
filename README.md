# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4.Predict the cluster and plot data graphs.
5. Print the output and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: A.SANJAI
RegisterNumber: 212220040142 
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![image](https://user-images.githubusercontent.com/95969295/204556693-8b8c3ea9-be1c-429a-b727-01d3fe761ea1.png)

![image](https://user-images.githubusercontent.com/95969295/204557693-b640d285-0bea-461c-9bd6-8b5a1c902c66.png)

![image](https://user-images.githubusercontent.com/95969295/204557797-2dcccd6d-0c98-4c50-a224-404b8b36f7d6.png)

![image](https://user-images.githubusercontent.com/95969295/204557944-eb5b4e2d-81e0-4a35-b607-2841e29be832.png)

![image](https://user-images.githubusercontent.com/95969295/204558030-b179bf64-03a6-476f-90f1-33a3d8268e61.png)

![image](https://user-images.githubusercontent.com/95969295/204558145-ec8b0aea-db0a-4d5b-a3d9-5534d6e06390.png)





## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
