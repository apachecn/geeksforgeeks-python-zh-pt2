# 通过给定的整数索引选择一行序列或数据帧

> 原文:[https://www . geesforgeks . org/按给定整数索引选择一行序列或数据帧/](https://www.geeksforgeeks.org/select-a-row-of-series-or-dataframe-by-given-integer-index/)

[**data frame . iloc【】**](https://www.geeksforgeeks.org/python-extracting-rows-using-pandas-iloc/)**用于通过给定的整数索引选择一行序列/数据帧。让我们创建一个数据框:**

****代号:****

 **## 蟒 3

```
# import pandas library
import pandas as pd 

# Create the dataframe 
df = pd.DataFrame({'ID': ['114', '345',
                         '157788', '5626'], 
                'Product': ['shirt', 'trousers',
                           'tie', 'belt'], 
                'Price': [1200, 1500,
                         600, 352], 
                'Color': ['White','Black', 
                         'Red', 'Brown'], 
                'Discount': [10, 10,
                            10, 10]}) 

# Show the dataframe
df
```**