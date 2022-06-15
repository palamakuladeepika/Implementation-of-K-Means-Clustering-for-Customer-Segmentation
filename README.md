# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the required packages. <br>2.Import the dataset to work on. <br>3.From sklearn module import kmeans. <br>4.Define number of clusters to be made. <br>5.Assign the cluster values.<br> 6.Plot the cluster using matplotlib.pyplot <br>7.End the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Palamakula Deepika.
RegisterNumber:  212221240035
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
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
plt.xlabel("no of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
data["cluster"] =y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4= data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="blue",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="red",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="orange",label="cluster4")
plt.title("Customer Segment")
plt.legend()
```

## Output:

<img width="164" alt="7 3" src="https://user-images.githubusercontent.com/94154679/173923159-4420580e-dad1-4b38-b096-83cbef65c2a2.png">

<img width="263" alt="7 2" src="https://user-images.githubusercontent.com/94154679/173923164-0cdb0c79-3855-4e79-8a8f-e11e820e08d3.png">


<img width="362" alt="7 1" src="https://user-images.githubusercontent.com/94154679/173923171-41f58068-7ca6-407c-8e13-c69aef15a65d.png">

<img width="284" alt="7 4" src="https://user-images.githubusercontent.com/94154679/173923157-e868a223-04ef-4d72-b29d-9eb02d27327b.png">


<img width="272" alt="7 5" src="https://user-images.githubusercontent.com/94154679/173923153-e52d5134-7708-4459-b66d-328ade567e6b.png">

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
