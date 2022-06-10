# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm 
step 1:
Import the necessary packages using import statement.

step 2:
Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

step 3:
Import KMeans and use for loop to cluster the data.

step 4:
Predict the cluster and plot data graphs.

step 5:
Print the outputs and end the program 

## Program:
```

Program to implement the K Means Clustering for Customer 
Segmentation.


Developed by: K.M.SWETHA
RegisterNumber: 212221240055 


import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head(
data.info())
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
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
### Data.head():
![image](https://user-images.githubusercontent.com/94228215/172998814-79a7e3bb-5bb5-4dba-8b14-9e9107d76988.png)


### Data.info():
![image](https://user-images.githubusercontent.com/94228215/172998831-01f5c85a-434a-48e7-89ad-9c4ef4154941.png)


### Data.isnull().sum():

![image](https://user-images.githubusercontent.com/94228215/172998866-bb1c14cb-34ea-4e91-b69e-294cc17b80ec.png)

### plt-Elbow Method:
![image](https://user-images.githubusercontent.com/94228215/172998903-3fd2c539-8a3d-4394-99a7-64ccc45572ee.png)


### Km.fit(data.iloc):
![image](https://user-images.githubusercontent.com/94228215/172998931-254e6a0a-a974-44f6-bc0b-a39918c3f1d6.png)


### plt-Customer Segments:

![image](https://user-images.githubusercontent.com/94228215/172998964-b76bfeee-59b0-46ef-bad8-0ca76a0c91a2.png)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
