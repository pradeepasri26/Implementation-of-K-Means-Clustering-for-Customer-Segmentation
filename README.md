# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import standard libraries in python for finding Implementation-of-K-Means-Clustering-for-Customer-Segmentation.

2.Initialize and print the data.head(),data.info(),data.isnull().sum()

3.Import sklearn.cluster import KMeans

4.Calculate the value of KMeans Clusters.

5.Plot the graph from Elbow method and find y_pred values .

6.Plot the graph from Customer Segments Graph. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: PRADEEPASRI S
RegisterNumber: 212221220038
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")

print("data.head() function:")
data.head()

print("data.info():")
data.info()

print("data.isnull().sum() function:")
data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[] #Within-Cluster Sum of Square.

for i in range(1,11):
kmeans=KMeans(n_clusters=i,init="k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
         
print("Elbow method Graph:")
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

print("KMeans clusters:")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

print("y_pred:")
y_pred=km.predict(data.iloc[:,3:])
y_pred

print("Customer segments Graph:")
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
## data.head()
![image](https://github.com/pradeepasri26/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433142/de437078-9ebd-4471-8527-72f962d6840b)
## data.info()
![image](https://github.com/pradeepasri26/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433142/a89cc80c-384c-4ab1-99e2-f0efda3cd99b)
## data.isnull().sum()
![image](https://github.com/pradeepasri26/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433142/1ee426e0-3030-498b-b20b-9d4589346148)
## Elbow method graph
![image](https://github.com/pradeepasri26/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433142/b6e95f19-c93b-4fcb-8976-d60116d0c07c)
## K Means clusters
![image](https://github.com/pradeepasri26/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433142/92d02ae1-5f43-447c-9c47-6b57100d4c9d)
## y_pred
![image](https://github.com/pradeepasri26/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433142/42e6a1ad-8c24-4290-a566-fcfecad19d7e)
## Customers Segments Graph
![image](https://github.com/pradeepasri26/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433142/49988a6d-200b-4eb6-9bd1-fd41c435f5b0)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
