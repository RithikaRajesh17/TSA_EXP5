# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 11-05-2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
data = pd.read_csv('/content/POPH.csv',parse_dates=['date'],index_col='date')
decomposition = seasonal_decompose(data['value'], model='additive',period=12)
plt.figure(figsize=(10, 12))
plt.subplot(411)
plt.plot(data['value'], label='Population')
plt.legend(loc='upper left')
plt.title(' Population')
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='green')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='red')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='blue')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
```
### OUTPUT:
ORIGINAL DATA:


<img width="534" height="146" alt="image" src="https://github.com/user-attachments/assets/ffe51257-9204-4868-9b53-2b6de407bc28" />




SEASONAL PLOT REPRESENTATION :

<img width="589" height="146" alt="image" src="https://github.com/user-attachments/assets/6cfe9ed1-3fed-4208-8a7f-821d123f5892" />


TREND PLOT REPRESENTATION :
<img width="534" height="146" alt="image" src="https://github.com/user-attachments/assets/ca322d85-c03d-4218-a580-2a226d62d5fd" />


OVERAL REPRESENTATION:

<img width="630" height="144" alt="image" src="https://github.com/user-attachments/assets/a17d6680-2999-4924-bf38-47a4607e6315" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
