```python
# import python libraries
import numpy as np 
import pandas as pd 
import matplotlib.pyplot as plt # visualizing data
%matplotlib inline
import seaborn as sns
```


```python
#import csv file
df= pd.read_csv('../../Python_Diwali_Sales_Analysis-main/Diwali Sales Data.csv', encoding='unicode_escape' )
```


```python
df.shape
```




    (11251, 15)




```python
df.head(10)
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>User_ID</th>
      <th>Cust_name</th>
      <th>Product_ID</th>
      <th>Gender</th>
      <th>Age Group</th>
      <th>Age</th>
      <th>Marital_Status</th>
      <th>State</th>
      <th>Zone</th>
      <th>Occupation</th>
      <th>Product_Category</th>
      <th>Orders</th>
      <th>Amount</th>
      <th>Status</th>
      <th>unnamed1</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1002903</td>
      <td>Sanskriti</td>
      <td>P00125942</td>
      <td>F</td>
      <td>26-35</td>
      <td>28</td>
      <td>0</td>
      <td>Maharashtra</td>
      <td>Western</td>
      <td>Healthcare</td>
      <td>Auto</td>
      <td>1</td>
      <td>23952.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1000732</td>
      <td>Kartik</td>
      <td>P00110942</td>
      <td>F</td>
      <td>26-35</td>
      <td>35</td>
      <td>1</td>
      <td>Andhra Pradesh</td>
      <td>Southern</td>
      <td>Govt</td>
      <td>Auto</td>
      <td>3</td>
      <td>23934.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1001990</td>
      <td>Bindu</td>
      <td>P00118542</td>
      <td>F</td>
      <td>26-35</td>
      <td>35</td>
      <td>1</td>
      <td>Uttar Pradesh</td>
      <td>Central</td>
      <td>Automobile</td>
      <td>Auto</td>
      <td>3</td>
      <td>23924.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1001425</td>
      <td>Sudevi</td>
      <td>P00237842</td>
      <td>M</td>
      <td>0-17</td>
      <td>16</td>
      <td>0</td>
      <td>Karnataka</td>
      <td>Southern</td>
      <td>Construction</td>
      <td>Auto</td>
      <td>2</td>
      <td>23912.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1000588</td>
      <td>Joni</td>
      <td>P00057942</td>
      <td>M</td>
      <td>26-35</td>
      <td>28</td>
      <td>1</td>
      <td>Gujarat</td>
      <td>Western</td>
      <td>Food Processing</td>
      <td>Auto</td>
      <td>2</td>
      <td>23877.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1000588</td>
      <td>Joni</td>
      <td>P00057942</td>
      <td>M</td>
      <td>26-35</td>
      <td>28</td>
      <td>1</td>
      <td>Himachal Pradesh</td>
      <td>Northern</td>
      <td>Food Processing</td>
      <td>Auto</td>
      <td>1</td>
      <td>23877.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1001132</td>
      <td>Balk</td>
      <td>P00018042</td>
      <td>F</td>
      <td>18-25</td>
      <td>25</td>
      <td>1</td>
      <td>Uttar Pradesh</td>
      <td>Central</td>
      <td>Lawyer</td>
      <td>Auto</td>
      <td>4</td>
      <td>23841.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1002092</td>
      <td>Shivangi</td>
      <td>P00273442</td>
      <td>F</td>
      <td>55+</td>
      <td>61</td>
      <td>0</td>
      <td>Maharashtra</td>
      <td>Western</td>
      <td>IT Sector</td>
      <td>Auto</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1003224</td>
      <td>Kushal</td>
      <td>P00205642</td>
      <td>M</td>
      <td>26-35</td>
      <td>35</td>
      <td>0</td>
      <td>Uttar Pradesh</td>
      <td>Central</td>
      <td>Govt</td>
      <td>Auto</td>
      <td>2</td>
      <td>23809.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1003650</td>
      <td>Ginny</td>
      <td>P00031142</td>
      <td>F</td>
      <td>26-35</td>
      <td>26</td>
      <td>1</td>
      <td>Andhra Pradesh</td>
      <td>Southern</td>
      <td>Media</td>
      <td>Auto</td>
      <td>4</td>
      <td>23799.99</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 11251 entries, 0 to 11250
    Data columns (total 15 columns):
     #   Column            Non-Null Count  Dtype  
    ---  ------            --------------  -----  
     0   User_ID           11251 non-null  int64  
     1   Cust_name         11251 non-null  object 
     2   Product_ID        11251 non-null  object 
     3   Gender            11251 non-null  object 
     4   Age Group         11251 non-null  object 
     5   Age               11251 non-null  int64  
     6   Marital_Status    11251 non-null  int64  
     7   State             11251 non-null  object 
     8   Zone              11251 non-null  object 
     9   Occupation        11251 non-null  object 
     10  Product_Category  11251 non-null  object 
     11  Orders            11251 non-null  int64  
     12  Amount            11239 non-null  float64
     13  Status            0 non-null      float64
     14  unnamed1          0 non-null      float64
    dtypes: float64(3), int64(4), object(8)
    memory usage: 1.3+ MB
    


```python
#drop unrelated/blank columns
df.drop(['Status', 'unnamed1'], axis=1, inplace=True)
```


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 11251 entries, 0 to 11250
    Data columns (total 13 columns):
     #   Column            Non-Null Count  Dtype  
    ---  ------            --------------  -----  
     0   User_ID           11251 non-null  int64  
     1   Cust_name         11251 non-null  object 
     2   Product_ID        11251 non-null  object 
     3   Gender            11251 non-null  object 
     4   Age Group         11251 non-null  object 
     5   Age               11251 non-null  int64  
     6   Marital_Status    11251 non-null  int64  
     7   State             11251 non-null  object 
     8   Zone              11251 non-null  object 
     9   Occupation        11251 non-null  object 
     10  Product_Category  11251 non-null  object 
     11  Orders            11251 non-null  int64  
     12  Amount            11239 non-null  float64
    dtypes: float64(1), int64(4), object(8)
    memory usage: 1.1+ MB
    


```python
#check for null values
pd.isnull(df).sum()
```




    User_ID              0
    Cust_name            0
    Product_ID           0
    Gender               0
    Age Group            0
    Age                  0
    Marital_Status       0
    State                0
    Zone                 0
    Occupation           0
    Product_Category     0
    Orders               0
    Amount              12
    dtype: int64




```python
df.shape
```




    (11251, 13)




```python
# drop null values
df.dropna(inplace=True)
```


```python
df.shape
```




    (11239, 13)




```python
# change data type
df['Amount']=df['Amount'].astype('int')
```


```python
df['Amount'].dtype
```




    dtype('int64')




```python
df.columns
```




    Index(['User_ID', 'Cust_name', 'Product_ID', 'Gender', 'Age Group', 'Age',
           'Marital_Status', 'State', 'Zone', 'Occupation', 'Product_Category',
           'Orders', 'Amount'],
          dtype='object')




```python
# describe() method returns description of the data in the DataFrame (i.e. count, mean, std, etc)
df.describe()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>User_ID</th>
      <th>Age</th>
      <th>Marital_Status</th>
      <th>Orders</th>
      <th>Amount</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1.123900e+04</td>
      <td>11239.000000</td>
      <td>11239.000000</td>
      <td>11239.000000</td>
      <td>11239.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.003004e+06</td>
      <td>35.410357</td>
      <td>0.420055</td>
      <td>2.489634</td>
      <td>9453.610553</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.716039e+03</td>
      <td>12.753866</td>
      <td>0.493589</td>
      <td>1.114967</td>
      <td>5222.355168</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000001e+06</td>
      <td>12.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>188.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1.001492e+06</td>
      <td>27.000000</td>
      <td>0.000000</td>
      <td>2.000000</td>
      <td>5443.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.003064e+06</td>
      <td>33.000000</td>
      <td>0.000000</td>
      <td>2.000000</td>
      <td>8109.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1.004426e+06</td>
      <td>43.000000</td>
      <td>1.000000</td>
      <td>3.000000</td>
      <td>12675.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1.006040e+06</td>
      <td>92.000000</td>
      <td>1.000000</td>
      <td>4.000000</td>
      <td>23952.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# use describe() for specific columns
df[['Age', 'Orders','Amount']].describe()
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Orders</th>
      <th>Amount</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>11239.000000</td>
      <td>11239.000000</td>
      <td>11239.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>35.410357</td>
      <td>2.489634</td>
      <td>9453.610553</td>
    </tr>
    <tr>
      <th>std</th>
      <td>12.753866</td>
      <td>1.114967</td>
      <td>5222.355168</td>
    </tr>
    <tr>
      <th>min</th>
      <td>12.000000</td>
      <td>1.000000</td>
      <td>188.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>27.000000</td>
      <td>2.000000</td>
      <td>5443.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>33.000000</td>
      <td>2.000000</td>
      <td>8109.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>43.000000</td>
      <td>3.000000</td>
      <td>12675.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>92.000000</td>
      <td>4.000000</td>
      <td>23952.000000</td>
    </tr>
  </tbody>
</table>
</div>



# Exploratory Data Analysis

### Gender


```python
# plotting a bar chart for Gender and it's count
ax=sns.countplot(x='Gender',data=df,palette=['#125B9A','#F05A7E'])
for bars in ax.containers:
    ax.bar_label(bars)
```

    C:\Users\Admin\AppData\Local\Temp\ipykernel_27304\2594912766.py:2: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      ax=sns.countplot(x='Gender',data=df,palette=['#125B9A','#F05A7E'])
    


    
![png](output_18_1.png)
    



```python
#plotting a bar chart for gender vs total amount

sns.set(rc={'figure.figsize':(6,5)})
sales_gen= df.groupby(['Gender'],as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)
sns.barplot(x='Gender', y='Amount',data=sales_gen,hue='Gender')
```




    <Axes: xlabel='Gender', ylabel='Amount'>




    
![png](output_19_1.png)
    


*From above graphs we can see that most of the buyers are females and even the purchasing power of females are greater than men.*

### Age


```python
ax=sns.countplot(data=df, x='Age Group',hue='Gender')
for bars in ax.containers:
    ax.bar_label(bars)
```


    
![png](output_22_0.png)
    



```python
# Total Amount vs Age Group
sales_age = df.groupby(['Age Group'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)

sns.barplot(x = 'Age Group',y= 'Amount' ,data = sales_age,hue='Age Group')
```




    <Axes: xlabel='Age Group', ylabel='Amount'>




    
![png](output_23_1.png)
    


*From above graphs we can see that most of the buyers are of age group between 26-35 yrs female*

### State


```python
#total number of orders from top 10 states
sales_state=df.groupby(['State'],as_index=False)['Orders'].sum().sort_values(by='Orders',ascending=False).head(10)
sns.set(rc={'figure.figsize':(15,5)})
sns.barplot(data=sales_state,x='State',y='Orders',hue='State')
```




    <Axes: xlabel='State', ylabel='Orders'>




    
![png](output_26_1.png)
    



```python
# total amount/sales from top 10 states
sales_state= df.groupby(['State'],as_index=False)['Amount'].sum().sort_values(by=['Amount'],ascending=False).head(10)
sns.set(rc={'figure.figsize':(15,5)})
sns.barplot(data=sales_state,x='State',y='Amount',hue='State')
```




    <Axes: xlabel='State', ylabel='Amount'>




    
![png](output_27_1.png)
    


*From above graphs we can see that most of the orders & total sales/amount are from Uttar Pradesh, Maharashtra and Karnataka respectively.*

### Marital Status


```python
ax=sns.countplot(data=df, x='Marital_Status', hue='Marital_Status')
sns.set(rc={'figure.figsize':(20,5)})
for bars in ax.containers:
   ax.bar_label(bars)
```


    
![png](output_30_0.png)
    



```python
sales_state=df.groupby(['Marital_Status','Gender'],as_index=False)['Amount'].sum().sort_values(by='Amount',ascending=False)
sns.set(rc={'figure.figsize':(6,5)})
sns.barplot(data=sales_state,x='Marital_Status',y='Amount',hue='Gender')
```




    <Axes: xlabel='Marital_Status', ylabel='Amount'>




    
![png](output_31_1.png)
    


*From above graphs we can see that most of the buyers are married (women) and they have high purchasing power*

### Occupation


```python
sns.set(rc={'figure.figsize':(20,5)})
ax=sns.countplot(data=df,x='Occupation',hue='Occupation')
for bars in ax.containers:
    ax.bar_label(bars)
```


    
![png](output_34_0.png)
    



```python
sales_state = df.groupby(['Occupation'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)

sns.set(rc={'figure.figsize':(20,5)})
sns.barplot(data = sales_state, x = 'Occupation',y= 'Amount',hue='Occupation')
```




    <Axes: xlabel='Occupation', ylabel='Amount'>




    
![png](output_35_1.png)
    


*From above graphs we can see that most of the buyers are working in IT, Healthcare and Aviation sector.*

### Product category


```python
sns.set(rc={'figure.figsize':(20,5)})
ax = sns.countplot(data = df, x = 'Product_Category',hue='Product_Category')

for bars in ax.containers:
    ax.bar_label(bars)
```


    
![png](output_38_0.png)
    



```python
sales_state = df.groupby(['Product_Category'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False).head(10)

sns.set(rc={'figure.figsize':(20,5)})
sns.barplot(data = sales_state, x = 'Product_Category',y= 'Amount',hue='Product_Category')
```




    <Axes: xlabel='Product_Category', ylabel='Amount'>




    
![png](output_39_1.png)
    


*From above graphs we can see that most of the sold products are from Food, Clothing and Electronics category.*


```python
sales_state = df.groupby(['Product_ID'], as_index=False)['Orders'].sum().sort_values(by='Orders', ascending=False).head(10)

sns.set(rc={'figure.figsize':(20,5)})
sns.barplot(data = sales_state, x = 'Product_ID',y= 'Orders',hue='Product_ID')
```




    <Axes: xlabel='Product_ID', ylabel='Orders'>




    
![png](output_41_1.png)
    



```python
# top 10 most sold products (same thing as above)

fig1, ax1 = plt.subplots(figsize=(12,7))
df.groupby('Product_ID')['Orders'].sum().nlargest(10).sort_values(ascending=False).plot(kind='bar')
```




    <Axes: xlabel='Product_ID'>




    
![png](output_42_1.png)
    


### Conclusion:

*Married women age group 26-35 yrs from UP, Maharastra and Karnataka working in IT, Healthcare and Aviation are more likely to buy products from Food, Clothing and Electronics category*
