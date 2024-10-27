# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
step 1. Start the program
step 2. Import pandas and matplotlib.pyplot
step 3. Read the dataset and transform it
step 4. Import KMeans and fit the data in the model
step 5. Plot the Cluster graph
step 6. End the program
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:KRITHIGA U 
RegisterNumber:  212223240076
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square. 
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])data.head() function
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
data.head() function

![image](https://github.com/user-attachments/assets/212b5f2b-c1a7-4b32-b6e8-58952530112c)

data.info()

![image](https://github.com/user-attachments/assets/a0db0c85-c63d-4c33-85d9-3e60aa554e7e)

data.isnull().sum() function

![image](https://github.com/user-attachments/assets/a8e0c491-5c33-4a1e-b2fa-0f607633bae2)

Elbow method Graph

![image](https://github.com/user-attachments/assets/79cc2e08-1b5e-4761-ba6e-4721396b05f1)

KMeans clusters

![image](https://github.com/user-attachments/assets/a062598e-b903-4bac-bcb9-d40532c6cdab)

Customer segments Graph

![image](https://github.com/user-attachments/assets/b8e949a9-4ada-4b9e-8a74-b553a183b955)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
