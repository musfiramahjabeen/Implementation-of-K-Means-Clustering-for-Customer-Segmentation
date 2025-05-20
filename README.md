# EXP10 - Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program.

## Program:
```python
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MUSFIRA MAHJABEEN M
RegisterNumber:  212223230130
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")

data.head()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Cluster")
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
#### Head values :
![Screenshot 2024-05-04 190353](https://github.com/MOHAMEDAHSAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331378/b90b21dd-5a64-40c5-9597-06539ea5f2bc)

<BR>

![Screenshot 2024-05-04 190401](https://github.com/MOHAMEDAHSAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331378/e8bb122d-8640-4e29-ba88-53131175317b)
#### Elbow Method graph :
![Screenshot 2024-05-04 190415](https://github.com/MOHAMEDAHSAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331378/abc5a509-f964-4def-a09f-c791a1fe869b)
![Screenshot 2024-05-04 190424](https://github.com/MOHAMEDAHSAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331378/8b7e76d1-37fd-432c-8bc0-96135e400e5b)
![Screenshot 2024-05-04 190433](https://github.com/MOHAMEDAHSAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331378/91cf56dd-7f77-4fcd-aed7-19147ce0bf29)





![Screenshot 2024-05-04 190440](https://github.com/MOHAMEDAHSAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331378/695ddbee-2911-470f-b83e-b66b6a2150e2)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
