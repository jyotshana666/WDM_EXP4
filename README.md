### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 19-09-2025
### NAME: Preethi D
### REG NO: 212224040250
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```
PROGRAM 1:

import pandas as pd
df = pd.read_csv(r"C:\Users\admin\Downloads\clustervisitor.csv")
cluster = {"Young": (df['Age'] <= 30),"Middle": ((df['Age'] > 30) & (df['Age'] <= 50)),"Old": (df['Age'] > 50)}
print(cluster)
count=[]
for g,c in cluster.items():
    visitors=df[c]
    count.append(len(visitors))
    print(f"visitors in {g} Group")
    print(visitors)
    print(count)
import matplotlib.pyplot as plt
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(),count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:

<img width="646" height="853" alt="image" src="https://github.com/user-attachments/assets/ab17e27c-268a-4d19-9aee-e516197d4822" />

<img width="1008" height="698" alt="image" src="https://github.com/user-attachments/assets/e1b00a8f-3ecd-4219-9d00-a6e5679fdce4" />


```
PROGRAM 2:

df = pd.read_csv(r"C:\Users\admin\Downloads\clustervisitor (Salary).csv")
df1 = df['Age']
df2 = df['Salary']
df3 = pd.concat([df1, df2], axis=1)
df3

from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

sc=StandardScaler()
scaleddata=sc.fit_transform(df3)
print(scaleddata)

kmeans=KMeans (n_clusters=3, random_state=42)
df3['cluster']=kmeans.fit_predict(df3)
df3

plt.scatter(df3 ['Age'], df3 ['Salary'],c=df3['cluster'])
plt.xlabel("Age")
plt.ylabel("Income in thousands")
plt.show()
```
### Output:

<img width="215" height="812" alt="image" src="https://github.com/user-attachments/assets/e1104dd1-888c-43d9-a59a-c635abee935d" />

<img width="1000" height="616" alt="image" src="https://github.com/user-attachments/assets/2f68ebb1-a4ed-441f-af23-66c05dbd7402" />



### Result:

Implementation of Cluster and Visitor Segmentation for Navigation patterns hasbeen done successfully.
