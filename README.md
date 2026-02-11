### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 07/02/2026
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

### Program1:
```py
import pandas as pd
import numpy as np
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt

df=pd.read_csv('C:\\Users\\nivle\\Downloads\\clustervisitor.csv')

cluster={'Young':(df['Age']<=30),'Middle':((df['Age'])>30 & (df['Age']<=50)),'Old':(df['Age']>50)}
count=[]
for group,condition in cluster.items():
  visitors=df[condition]
  count.append(len(visitors))
  print(f"The Visitors on {group} are")
  print(visitors)
  print("count =",len(visitors))
```
### Output:
<img width="306" height="785" alt="image" src="https://github.com/user-attachments/assets/f9b872b1-cba3-4e7f-b939-9b1fa114c977" />

### Program 2
```py
pandas_df = pd.DataFrame(df)
np.random.seed(42) # for reproducibility
income = np.random.randint(30, 120, size=len(pandas_df)) * 1000
pandas_df['Income'] = income

# Save the updated DataFrame to a new CSV file
pandas_df.to_csv('C:\\Users\\nivle\\Downloads\\clustervisitor.csv', index=False)

print("Added 'Income' column to the DataFrame and saved it as 'clustervisitor_with_income.csv'.")
print("Here's the updated DataFrame:")
display(pandas_df)
```
### Output:

<img width="546" height="842" alt="image" src="https://github.com/user-attachments/assets/f82893d3-f1d5-481d-871f-ee082ca65687" />


### Program 3(visualization):

```py
plt.figure(figsize=(8, 6))
plt.bar(['Young','Middle','Old'], count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
<img width="178" height="803" alt="image" src="https://github.com/user-attachments/assets/5595dc03-4f84-40da-9a9d-c006777f3a94" />

### Visualization:
```
plt.figure(figsize=(8,6))
plt.scatter(x=df3['Age'],y=df3['income'],c= df3['cluster'])
plt.xlabel('Age')
plt.ylabel('income')
plt.title('Kmeans Cluster')
plt.show()
```
### Output:
<img width="659" height="461" alt="image" src="https://github.com/user-attachments/assets/76792424-8589-4675-aa1c-517fab60b943" />

### Result:

Thus, cluster and Visitor Segmentation for Navigation patterns have been implemented successfully.
