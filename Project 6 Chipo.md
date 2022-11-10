# Ex2 - Getting and Knowing your Data

This time we are going to pull data directly from the internet.
Special thanks to: https://github.com/justmarkham for sharing the dataset and materials.

### Step 1. Import the necessary libraries


```python
import pandas as pd 
import numpy as np 
```

### Step 2. Import the dataset from this [address](https://raw.githubusercontent.com/justmarkham/DAT8/master/data/chipotle.tsv). 

### Step 3. Assign it to a variable called chipo.


```python
df = pd.read_table("https://raw.githubusercontent.com/justmarkham/DAT8/master/data/chipotle.tsv")
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>order_id</th>
      <th>quantity</th>
      <th>item_name</th>
      <th>choice_description</th>
      <th>item_price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>1</td>
      <td>Chips and Fresh Tomato Salsa</td>
      <td>NaN</td>
      <td>$2.39</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>1</td>
      <td>Izze</td>
      <td>[Clementine]</td>
      <td>$3.39</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>1</td>
      <td>Nantucket Nectar</td>
      <td>[Apple]</td>
      <td>$3.39</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>1</td>
      <td>Chips and Tomatillo-Green Chili Salsa</td>
      <td>NaN</td>
      <td>$2.39</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>2</td>
      <td>Chicken Bowl</td>
      <td>[Tomatillo-Red Chili Salsa (Hot), [Black Beans...</td>
      <td>$16.98</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>4617</th>
      <td>1833</td>
      <td>1</td>
      <td>Steak Burrito</td>
      <td>[Fresh Tomato Salsa, [Rice, Black Beans, Sour ...</td>
      <td>$11.75</td>
    </tr>
    <tr>
      <th>4618</th>
      <td>1833</td>
      <td>1</td>
      <td>Steak Burrito</td>
      <td>[Fresh Tomato Salsa, [Rice, Sour Cream, Cheese...</td>
      <td>$11.75</td>
    </tr>
    <tr>
      <th>4619</th>
      <td>1834</td>
      <td>1</td>
      <td>Chicken Salad Bowl</td>
      <td>[Fresh Tomato Salsa, [Fajita Vegetables, Pinto...</td>
      <td>$11.25</td>
    </tr>
    <tr>
      <th>4620</th>
      <td>1834</td>
      <td>1</td>
      <td>Chicken Salad Bowl</td>
      <td>[Fresh Tomato Salsa, [Fajita Vegetables, Lettu...</td>
      <td>$8.75</td>
    </tr>
    <tr>
      <th>4621</th>
      <td>1834</td>
      <td>1</td>
      <td>Chicken Salad Bowl</td>
      <td>[Fresh Tomato Salsa, [Fajita Vegetables, Pinto...</td>
      <td>$8.75</td>
    </tr>
  </tbody>
</table>
<p>4622 rows × 5 columns</p>
</div>



### Step 4. See the first 10 entries


```python
df.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>order_id</th>
      <th>quantity</th>
      <th>item_name</th>
      <th>choice_description</th>
      <th>item_price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>1</td>
      <td>Chips and Fresh Tomato Salsa</td>
      <td>NaN</td>
      <td>$2.39</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>1</td>
      <td>Izze</td>
      <td>[Clementine]</td>
      <td>$3.39</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>1</td>
      <td>Nantucket Nectar</td>
      <td>[Apple]</td>
      <td>$3.39</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>1</td>
      <td>Chips and Tomatillo-Green Chili Salsa</td>
      <td>NaN</td>
      <td>$2.39</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>2</td>
      <td>Chicken Bowl</td>
      <td>[Tomatillo-Red Chili Salsa (Hot), [Black Beans...</td>
      <td>$16.98</td>
    </tr>
    <tr>
      <th>5</th>
      <td>3</td>
      <td>1</td>
      <td>Chicken Bowl</td>
      <td>[Fresh Tomato Salsa (Mild), [Rice, Cheese, Sou...</td>
      <td>$10.98</td>
    </tr>
    <tr>
      <th>6</th>
      <td>3</td>
      <td>1</td>
      <td>Side of Chips</td>
      <td>NaN</td>
      <td>$1.69</td>
    </tr>
    <tr>
      <th>7</th>
      <td>4</td>
      <td>1</td>
      <td>Steak Burrito</td>
      <td>[Tomatillo Red Chili Salsa, [Fajita Vegetables...</td>
      <td>$11.75</td>
    </tr>
    <tr>
      <th>8</th>
      <td>4</td>
      <td>1</td>
      <td>Steak Soft Tacos</td>
      <td>[Tomatillo Green Chili Salsa, [Pinto Beans, Ch...</td>
      <td>$9.25</td>
    </tr>
    <tr>
      <th>9</th>
      <td>5</td>
      <td>1</td>
      <td>Steak Burrito</td>
      <td>[Fresh Tomato Salsa, [Rice, Black Beans, Pinto...</td>
      <td>$9.25</td>
    </tr>
  </tbody>
</table>
</div>



### Step 5. What is the number of observations in the dataset?


```python
# Solution 1
len(df)
```




    4622




```python
# Solution 2

df.count()[0]
```




    4622



### Step 6. What is the number of columns in the dataset?


```python
len(df.columns)
```




    5



### Step 7. Print the name of all the columns.


```python
print(df.columns)
```

    Index(['order_id', 'quantity', 'item_name', 'choice_description',
           'item_price'],
          dtype='object')
    

### Step 8. How is the dataset indexed?


```python
df.index
```




    RangeIndex(start=0, stop=4622, step=1)



### Step 9. Which was the most-ordered item? 


```python
c = df.groupby('item_name').sum()
c = c.sort_values(['quantity'], ascending = False)
c.head(2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>order_id</th>
      <th>quantity</th>
    </tr>
    <tr>
      <th>item_name</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Chicken Bowl</th>
      <td>713926</td>
      <td>761</td>
    </tr>
    <tr>
      <th>Chicken Burrito</th>
      <td>497303</td>
      <td>591</td>
    </tr>
  </tbody>
</table>
</div>



### Step 10. For the most-ordered item, how many items were ordered?


```python
print('For the most-ordered item, ordered were:',str(713926))
```

    For the most-ordered item, ordered were: 713926
    

### Step 11. What was the most ordered item in the choice_description column?


```python
d = df.groupby('choice_description').sum()
d = d.sort_values(['quantity'], ascending = False)
d.head(2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>order_id</th>
      <th>quantity</th>
    </tr>
    <tr>
      <th>choice_description</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>[Diet Coke]</th>
      <td>123455</td>
      <td>159</td>
    </tr>
    <tr>
      <th>[Coke]</th>
      <td>122752</td>
      <td>143</td>
    </tr>
  </tbody>
</table>
</div>



### Step 12. How many items were orderd in total?


```python
total = df.quantity.sum()
total
```




    4972



### Step 13. Turn the item price into a float

#### Step 13.a. Check the item price type


```python
df.item_price.dtype
```




    dtype('O')



#### Step 13.b. Create a lambda function and change the type of item price


```python
try:
    dollarizer = lambda x: float(x[1:-1])
    df.item_price = df.item_price.apply(dollarizer)
    
except:TypeError 


```

#### Step 13.c. Check the item price type


```python
df.item_price.dtype
```




    dtype('float64')



### Step 14. How much was the revenue for the period in the dataset?


```python
revenue = (df['quantity'] * df['item_price']).sum()

print('Revenue was: $' + str(np.round(revenue,2)))
```

    Revenue was: $39237.02
    

### Step 15. How many orders were made in the period?


```python
orders = df.order_id.value_counts().count()
orders
```




    1834



### Step 16. What is the average revenue amount per order?


```python
# Solution 1

df['revenue'] = df['quantity'] * df['item_price']
d = order_grouped = df.groupby(by=['order_id']).sum()
order_grouped.mean()['revenue']
```




    21.394231188658654




```python
# Solution 2

df.groupby("order_id").sum().mean()["revenue"]
```




    21.394231188658654



### Step 17. How many different items are sold?


```python
df.item_name.value_counts().count()
```




    50




```python

```
