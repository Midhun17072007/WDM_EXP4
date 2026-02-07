### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 07-02-2026
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

### Program 1:
```python
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("clustervisitor.csv")
cluster = {"young" : (df['Age'] <= 30) , "middle" : (df['Age'] > 30) & (df['Age'] <= 50) , "old" : (df['Age'] > 50)}
count = []
for group , condition in cluster.items():
  visitors = df[condition]
  count.append(len(visitors))
  print(f"visitors in {group} age are\n")
  print(visitors)
  print("\n")
  print(visitor_count)
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(), count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()

```
### Output:

<img width="351" height="806" alt="image" src="https://github.com/user-attachments/assets/fdaab0df-2a94-44f9-8de4-acde065b5fa1" />

<img width="1007" height="793" alt="image" src="https://github.com/user-attachments/assets/a1eff2de-6c3d-417d-8e47-1d43b3d1650e" />



### Program 2:
```python
# Create a list to store counts of visitors in each age group
import pandas as pd
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt
df = pd.read_csv("clustervisitor_income.csv")
X = df[['Age' , 'Income']]
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
kmeans = KMeans(n_clusters = 4 , random_state = 42)
df['Cluster'] = kmeans.fit_predict(X_scaled)
print(df,"\n")
plt.scatter(df['Age'],df['Income'],c = df['Cluster'])
plt.xlabel('Age')
plt.ylabel('Salary in thousands')
plt.title('Kmeans Cluster')
plt.show()
```
### Output:

<img width="567" height="664" alt="image" src="https://github.com/user-attachments/assets/97360ca5-5a55-41de-8d2d-9b861a972f23" />

<img width="809" height="613" alt="image" src="https://github.com/user-attachments/assets/ec46d999-785d-445e-9693-45101821042e" />




### Result:

Thus, cluster and Visitor Segmentation for Navigation patterns have been implemented successfully.
