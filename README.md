# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 20-04-2026

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
df=pd.read_csv("/content/amazon_sales_data 2025.csv")
df.head()

df['Date']=pd.to_datetime(df['Date'])
df_agg = df.groupby('Date')['Quantity'].sum().reset_index()
df_agg.set_index('Date',inplace=True)

df_resampled = df_agg['Quantity'].resample('D').interpolate()
df_resampled.plot(kind='line',label='Total Sales', color='black')
plt.title('Time Series Plot of Number of passengers ecah day')
plt.xlabel('Day')
plt.ylabel( 'Number of passengers')
plt.legend()
plt.grid(True)
plt.show()



```










# OUTPUT:

<img width="847" height="625" alt="image" src="https://github.com/user-attachments/assets/51cde68b-1997-4b8b-a06d-a05dccd38746" />





# RESULT:
Thus we have created the python code for plotting the time series of given data.
