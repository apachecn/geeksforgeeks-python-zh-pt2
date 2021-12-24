# Python |用列平均值替换 NaN 值

> 原文:[https://www . geesforgeks . org/python-replace-nan-values-with-average-columns/](https://www.geeksforgeeks.org/python-replace-nan-values-with-average-of-columns/)

在机器学习和数据分析中，数据可视化是最重要的步骤之一。清理和排列数据是通过不同的算法完成的。有时在数据集中，我们得到 NaN(不是一个数字)值，这些值不可能用于数据可视化。

为了解决这个问题，一种可能的方法是用列的平均值替换 *nan* 值。下面给出了几个解决这个问题的方法。

**方法一:使用`np.colmean``np.take`**

```
# Python code to demonstrate
# to replace nan values
# with an average of columns

import numpy as np

# Initialising numpy array
ini_array = np.array([[1.3, 2.5, 3.6, np.nan], 
                      [2.6, 3.3, np.nan, 5.5],
                      [2.1, 3.2, 5.4, 6.5]])

# printing initial array
print ("initial array", ini_array)

# column mean
col_mean = np.nanmean(ini_array, axis = 0)

# printing column mean
print ("columns mean", str(col_mean))

# find indices where nan value is present
inds = np.where(np.isnan(ini_array))

# replace inds with avg of column
ini_array[inds] = np.take(col_mean, inds[1])

# printing final array
print ("final array", ini_array)
```

**输出:**

```
initial array [[ 1.3  2.5  3.6  nan]
 [ 2.6  3.3  nan  5.5]
 [ 2.1  3.2  5.4  6.5]]
columns mean [ 2\.   3\.   4.5  6\. ]

final array [[ 1.3  2.5  3.6  6\. ]
 [ 2.6  3.3  4.5  5.5]
 [ 2.1  3.2  5.4  6.5]]

```

**方法 2:使用`np.ma`和`np.where`**

```
# Python code to demonstrate
# to replace nan values
# with average of columns

import numpy as np

# Initialising numpy array
ini_array = np.array([[1.3, 2.5, 3.6, np.nan],
                      [2.6, 3.3, np.nan, 5.5],
                      [2.1, 3.2, 5.4, 6.5]])

# printing initial array
print ("initial array", ini_array)

# replace nan with col means
res = np.where(np.isnan(ini_array), np.ma.array(ini_array,
               mask = np.isnan(ini_array)).mean(axis = 0), ini_array)   

# printing final array
print ("final array", res)
```

**输出:**

```
initial array [[ 1.3  2.5  3.6  nan]
 [ 2.6  3.3  nan  5.5]
 [ 2.1  3.2  5.4  6.5]]
final array [[ 1.3  2.5  3.6  6\. ]
 [ 2.6  3.3  4.5  5.5]
 [ 2.1  3.2  5.4  6.5]]

```

**方法 3:使用天真和`zip`T2】**

```
# Python code to demonstrate
# to replace nan values
# with average of columns

import numpy as np

# Initialising numpy array
ini_array = np.array([[1.3, 2.5, 3.6, np.nan],
                      [2.6, 3.3, np.nan, 5.5],
                      [2.1, 3.2, 5.4, 6.5]])

# printing initial array
print ("initial array", ini_array)

# indices where values is nan in array
indices = np.where(np.isnan(ini_array))

# Iterating over numpy array to replace nan with values
for row, col in zip(*indices):
    ini_array[row, col] = np.mean(ini_array[
           ~np.isnan(ini_array[:, col]), col])

# printing final array
print ("final array", ini_array)
```

**输出:**

```
initial array [[ 1.3  2.5  3.6  nan]
 [ 2.6  3.3  nan  5.5]
 [ 2.1  3.2  5.4  6.5]]
final array [[ 1.3  2.5  3.6  6\. ]
 [ 2.6  3.3  4.5  5.5]
 [ 2.1  3.2  5.4  6.5]]

```