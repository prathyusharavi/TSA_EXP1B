# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 11-03-2025

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
### IMPORT THE NECESSARY PACKAGES
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
### LOAD DATASET
```
data=pd.read_csv('50startups.csv')
```
### PLoT THE DATA WITHOUT CONVERSION 

```
x=data['Profit']
y=data['Administration']
plt.xlabel('Profit')
plt.ylabel('Administration')
plt.plot(x,y)
```
### REGULAR  DIFFERENCING
```
data1=data
data1['diff']=data1['Administration'].diff()
x=data1['Profit']
y=data1['diff']
plt.xlabel('Profit')
plt.ylabel('Administration')
plt.plot(x,y)
```
### SEASONAL ADJUSTMENT
```
data2=data
data2['SeasonalAdjustment'] = data1['Administration'].rolling(window=12).mean() 
data2['SeasonalAdjustment'].dropna()
x=data2['Profit']
y=data2["SeasonalAdjustment"]
plt.xlabel('Profit')
plt.ylabel('Administration')
plt.plot(x,y)
```
### LOG TRANSFORMATION
```
data2=data
data2['log']=np.log(data2['diff']).dropna()
data2=data2.dropna()
x=data2['Profit']
y=data2['log']
plt.xlabel('Profit')
plt.ylabel('Administration')
plt.plot(x,y)
```

### OUTPUT:

WITHOUT CONVERSION

![image](https://github.com/user-attachments/assets/4cb303a1-8c44-426a-9985-8e2706843e15)

REGULAR DIFFERENCING:
![image](https://github.com/user-attachments/assets/2c5b5f3f-5a15-4ed8-9062-2c35f5052c0b)

SEASONAL ADJUSTMENT:
![image](https://github.com/user-attachments/assets/3c71aedc-1b79-4cd6-a973-223dba91dd53)

LOG TRANSFORMATION:
![image](https://github.com/user-attachments/assets/6c96edb4-8cd5-4c37-865f-06be54aa3744)

### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
