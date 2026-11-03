# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 30:11:2026

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt

# Read the dataset
df = pd.read_csv('temperature.csv')

# Remove empty rows
df = df.dropna(how='all')

# Convert temperature columns into numbers
cols = ['ANNUAL', 'JAN-FEB', 'MAR-MAY', 'JUN-SEP', 'OCT-DEC']

for col in cols:
    df[col] = pd.to_numeric(df[col], errors='coerce')

# Calculate mean temperature
print("Mean Temperature:")
print(df[cols].mean())

# Plot annual and seasonal temperature
plt.plot(df['YEAR'], df['ANNUAL'], label='ANNUAL')
plt.plot(df['YEAR'], df['JAN-FEB'], label='JAN-FEB')
plt.plot(df['YEAR'], df['MAR-MAY'], label='MAR-MAY')
plt.plot(df['YEAR'], df['JUN-SEP'], label='JUN-SEP')
plt.plot(df['YEAR'], df['OCT-DEC'], label='OCT-DEC')

# Add title and labels
plt.title('Annual and Seasonal Temperature')
plt.xlabel('YEAR')
plt.ylabel('TEMPERATURE')

# Display legend and grid
plt.legend()
plt.grid()

# Display graph
plt.show()
```











# OUTPUT:
<img width="806" height="712" alt="image" src="https://github.com/user-attachments/assets/65cbe285-4cb6-4b09-9a09-6e321ba92422" />







# RESULT:
Thus we have created the python code for plotting the time series of given data.
