### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 22/5/2026
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
```python
import pandas as pd
df = pd.read_csv('clustervisitor.csv')

cluster = {
    'Young': df['Age'] <= 30,
    'Middle-aged': (df['Age'] > 30) & (df['Age'] <= 50),
    'Elderly': df['Age'] > 50
}
count =[]
for g, v in cluster.items():  
    visitors = df[v] 
    print(f"Visitors in {g} are\n",visitors)
    print("Visitor count",len(visitors))
    count.append(len(visitors))
```
### Output:
![alt text](output/out.png)

### Visualization:
```python
import matplotlib.pyplot as plt
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(), count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
![alt text](output/plot.png)

### Result:
Thus the cluster and visitor segmentation for navigation patterns was implemented successfully in python.
