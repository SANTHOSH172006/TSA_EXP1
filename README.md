# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 05-02-2026

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
from matplotlib import pyplot as plt
import pandas as pd

df = pd.read_csv("/kaggle/input/dataset-ex1/ecommerce_sales_data (2).csv")

df.head()

df['Order Date'] = pd.to_datetime(df['Order Date'])

df = df.groupby('Order Date')['Sales'].sum().reset_index()

df.set_index('Order Date', inplace=True)

df_resampled = df['Sales'].resample('D').interpolate()

df_resampled.plot(kind='line', label='Total Sales', color='black')

plt.title('Time Series Plot of E-commerce Sales per Day')
plt.xlabel('Day')
plt.ylabel('Sales')
plt.legend()
plt.grid(True)
plt.show()

```










# OUTPUT:
<img width="905" height="606" alt="image" src="https://github.com/user-attachments/assets/8987c1f0-fd78-45d4-ab8e-0483eca4af40" />







# RESULT:
Thus we have created the python code for plotting the time series of given data.
