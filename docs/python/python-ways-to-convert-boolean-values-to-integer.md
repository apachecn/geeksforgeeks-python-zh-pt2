# Python |将布尔值转换为整数的方法

> 原文:[https://www . geesforgeks . org/python-将布尔值转换为整数的方法/](https://www.geeksforgeeks.org/python-ways-to-convert-boolean-values-to-integer/)

给定一个布尔值，编写一个 Python 程序将它们分别转换成整数值或列表。下面给出了几个解决上述任务的方法。
**方法#1:使用 int()方法**

## 蟒蛇 3

```py
# Python code to demonstrate
# to convert boolean value to integer

# Initialising Values
bool_val = True

# Printing initial Values
print("Initial value", bool_val)

# Converting boolean to integer
bool_val = int(bool_val == True)

# Printing result
print("Resultant value", bool_val)

```

**Output:** 

```py
Initial value True
Resultant value 1
```

**方法 2:使用天真方法**

## 蟒蛇 3

```py
# Python code to demonstrate
# to convert boolean
# value to integer

# Initialising Values
bool_val = True

# Printing initial Values
print("Initial value", bool_val)

# Converting boolean to integer
if bool_val:
    bool_val = 1
else:
    bool_val = 0
# Printing result
print("Resultant value", bool_val)

```

**Output:** 

```py
Initial value True
Resultant value 1
```

**方法#3:使用 numpy**
在存在布尔列表的情况下

## 蟒蛇 3

```py
# Python code to demonstrate
# to convert boolean
# value to integer

import numpy
# Initialising Values
bool_val = numpy.array([True, False])

# Printing initial Values
print("Initial values", bool_val)

# Converting boolean to integer
bool_val = numpy.multiply(bool_val, 1)
# Printing result
print("Resultant values", str(bool_val))
```

**Output:** 

```py
Initial values [ True False]
Resultant values [1 0]
```

**方法#4:在存在布尔列表的情况下使用地图()**

## 蟒蛇 3

```py
# Python code to demonstrate
# to convert boolean
# value to integer

# Initialising Values
bool_val = [True, False]

# Printing initial Values
print("Initial value", bool_val)

# Converting boolean to integer
bool_val = list(map(int, bool_val))

# Printing result
print("Resultant value", str(bool_val))
```

**Output:** 

```py
Initial value [True, False]
Resultant value [1, 0]
```