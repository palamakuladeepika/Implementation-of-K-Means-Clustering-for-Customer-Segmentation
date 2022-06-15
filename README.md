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
<img width="430" alt="6 1" src="https://user-images.githubusercontent.com/94154679/173922876-e63a5937-5c76-490b-bd7d-a709821eb1cd.png">

<img width="430" alt="6 2" src="https://user-images.githubusercontent.com/94154679/173922902-2e4ec74f-505f-4a57-84ee-5f7c20b81f9a.png">

<img width="430" alt="6 3" src="https://user-images.githubusercontent.com/94154679/173922940-764a4413-8454-4b27-a3fa-63091bed8acf.png">

<img width="760" alt="6 4" src="https://user-images.githubusercontent.com/94154679/173922991-39dd21f0-df09-4e8e-a52f-667a7ef3d487.png">

<img width="320" alt="6 5" src="https://user-images.githubusercontent.com/94154679/173923027-ad5e359a-0b39-4df4-8815-e945a3989b19.png">



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
