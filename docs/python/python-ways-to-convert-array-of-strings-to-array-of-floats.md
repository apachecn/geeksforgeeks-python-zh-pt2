# Python |将字符串数组转换为浮点数组的方法

> 原文:[https://www . geesforgeks . org/python-将字符串数组转换为浮点数组的方法/](https://www.geeksforgeeks.org/python-ways-to-convert-array-of-strings-to-array-of-floats/)

有时在竞争的编码环境中，我们在一些其他数据类型中获得输入，我们需要以其他形式转换它们这个问题与我们有字符串形式的输入相同，我们需要将其转换为浮点数。
我们来讨论几个将字符串数组转换成浮点数组的方法。
**方法#1:使用原型**

## 蟒蛇 3

```py
# Python code to demonstrate converting
# array of strings to array of floats
# using astype

import numpy as np

# initialising array
ini_array = np.array(["1.1", "1.5", "2.7", "8.9"])

# printing initial array
print ("initial array", str(ini_array))

# converting to array of floats
# using np.astype
res = ini_array.astype(np.float)

# printing final result
print ("final array", str(res))
```

**Output:** 

```py
initial array ['1.1' '1.5' '2.7' '8.9']
final array [ 1.1  1.5  2.7  8.9]
```

**方法 2:使用**字符串

## 蟒蛇 3

```py
# Python code to demonstrate converting
# array of strings to array of floats
# using fromstring

import numpy as np

# initialising array
ini_array = np.array(["1.1", "1.5", "2.7", "8.9"])

# printing initial array
print ("initial array", str(ini_array))

# converting to array of floats
# using np.fromstring
ini_array = ', '.join(ini_array)
ini_array = np.fromstring(ini_array, dtype = np.float,
                                           sep =', ' )

# printing final result
print ("final array", str(ini_array))
```

**Output:** 

```py
initial array ['1.1' '1.5' '2.7' '8.9']
final array [ 1.1  1.5  2.7  8.9]
```

**方法#3:使用 np.asarray()并键入**

## 蟒蛇 3

```py
# Python code to demonstrate
# converting array of strings to array of floats
# using asarray

import numpy as np

# initialising array
ini_array = np.array(["1.1", "1.5", "2.7", "8.9"])

# printing initial array
print ("initial array", str(ini_array))

# converting to array of floats
# using np.asarray
final_array = b = np.asarray(ini_array,
        dtype = np.float64, order ='C')

# printing final result
print ("final array", str(final_array))
```

**Output:** 

```py
initial array ['1.1' '1.5' '2.7' '8.9']
final array [ 1.1  1.5  2.7  8.9]
```