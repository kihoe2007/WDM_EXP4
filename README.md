### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 21/11/2026
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
# Import required libraries
import pandas as pd
import matplotlib.pyplot as plt

# Read the CSV file
data = pd.read_csv("visitors.csv")

# Display the data
print("Visitor Data:")
print(data)

# Define age groups using Boolean conditions
age_groups = {
    "Young": data[data["Age"] < 25],
    "Adult": data[(data["Age"] >= 25) & (data["Age"] < 40)],
    "Senior": data[data["Age"] >= 40]
}

# Display visitors in each age group
print("\nVisitor Segmentation:")
for group, visitors in age_groups.items():
    print(f"\n{group}:")
    print(visitors)

# Create a list to store the number of visitors
visitor_counts = []

# Count visitors in each age group
for group in age_groups:
    visitor_counts.append(len(age_groups[group]))

# Define labels for the bar chart
age_group_labels = list(age_groups.keys())

# Display the counts
print("\nVisitor Counts:")
for label, count in zip(age_group_labels, visitor_counts):
    print(f"{label}: {count}")

# Create the bar chart
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color="skyblue")
plt.xlabel("Age Groups")
plt.ylabel("Number of Visitors")
plt.title("Visitor Distribution Across Age Groups")
plt.show()
```
### Output:
<img width="737" height="576" alt="Screenshot 2026-08-04 113330" src="https://github.com/user-attachments/assets/1bb58fc8-4939-4da4-89f7-0309363eea5e" />


### Result:
Thus Cluster and Visitor Segmentation for Navigation patterns in Python is implemented.
