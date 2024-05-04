# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Start
2. Intialization and Assigning data points to clusters
3. Update centroids
4. Repeat
5. Output
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: H MOHAMED FARIKH
RegisterNumber: 212223080032 
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
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
Data head:

![Screenshot 2024-05-04 112736](https://github.com/MOHAMEDFARIKH2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/168570140/98dfe72c-dffc-46f2-802a-3542a20c5888)


Data info:

![Screenshot 2024-05-04 120601](https://github.com/MOHAMEDFARIKH2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/168570140/a1b439e9-16c9-428f-ba7a-f13785337d1b)


Data isnull().sum():

![Screenshot 2024-05-04 120607](https://github.com/MOHAMEDFARIKH2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/168570140/001c2bda-68a2-4121-84ce-cb34d7d90a91)



Plotting graph for elbow method:

![Screenshot 2024-05-04 113309](https://github.com/MOHAMEDFARIKH2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/168570140/3de0ba34-f806-4ed1-8f8d-f39168d49064)

Y_pred:

![Screenshot 2024-05-04 113536](https://github.com/MOHAMEDFARIKH2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/168570140/0c0467fa-b3b2-4caa-9fb1-02c27a3f7906)


Predicting and plotting graph for the clusters:

![Screenshot 2024-05-04 114112](https://github.com/MOHAMEDFARIKH2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/168570140/85e34bf2-ef54-434b-9ea0-0d3809cfae41)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
