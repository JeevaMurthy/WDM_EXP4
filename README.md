### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 
### AIM: 
To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
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

### Program 1:
```python
import pandas as pd
df=pd.read_csv("/content/clustervisitor.csv")
df.head()
cluster={"young":(df['Age']<=30),"Middle":((df['Age']>30)&(df['Age']<=60)),"Old":(df['Age']>50)}
cluster
count=[]
for g,c in cluster.items():
    visitor=df[c]
    count.append(len(visitor))
    print(f"Visitors in {g} group")
    print(visitor)
    print(count)
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt
plt.bar(cluster.keys(),count,data=df)
plt.xlabel('Age Group')
plt.show()
```
### Output:
<img width="508" height="596" alt="image" src="https://github.com/user-attachments/assets/c7990259-69a3-478a-9482-cac6d7e19d17" />
<img width="510" height="368" alt="image" src="https://github.com/user-attachments/assets/836cee7a-110f-4e41-bad9-7bab9b6b6aac" />

### Program 2:
```python
kmeans = KMeans(n_clusters=3, random_state=42)
df['Cluster'] = kmeans.fit_predict(df[['Age']])
print(df)
plt.scatter(df['User_ID'], df['Age'], c=df['Cluster'])
plt.xlabel('User_ID')
plt.ylabel('Age')
plt.title('K-Means')
plt.show()
```
### Output:
<img width="444" height="450" alt="image" src="https://github.com/user-attachments/assets/45462fcd-740d-4df9-b0a9-c88c81ce9136" />
</br>
<img width="480" height="384" alt="image" src="https://github.com/user-attachments/assets/400f0322-c26b-45d4-aae2-56347397d29a" />

### Result:
The implement Cluster and Visitor Segmentation for Navigation patterns in Python is execute successfully
