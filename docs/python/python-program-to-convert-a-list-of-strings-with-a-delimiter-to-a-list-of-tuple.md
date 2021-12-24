# Python 程序将带分隔符的字符串列表转换为元组列表

> 原文:[https://www . geesforgeks . org/python-program-to-convert-a-list-strings-with-delimiter-to-list-tuple/](https://www.geeksforgeeks.org/python-program-to-convert-a-list-of-strings-with-a-delimiter-to-a-list-of-tuple/)

给定包含带有特定分隔符的字符串的列表。任务是移除分隔符并将字符串转换为元组列表。

**示例:**

> **输入** : test_list = ["1-2 "、" 3-4-8-9"]，K = "-"
> **输出** : [(1，2)，(3，4，8，9)]
> **解释**:拆分后，1-2 = > (1，2)。
> 
> **输入**:test _ list =[“1 * 2”、“3 * 4 * 8 * 9”]，K =“*”
> **输出** : [(1，2)、(3，4，8，9)]
> **解释**:拆分后，1*2 = > (1，2)。

**方法一:使用列表理解+拆分()**

在这种情况下，首先使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 分割每个字符串，以 K 作为参数，然后使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)将这扩展到所有字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert K delim Strings to Integer Tuple List
# Using list comprehension + split()

# initializing list
test_list = ["1-2", "3-4-8-9", "4-10-4"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = "-"

# conversion using split and list comprehension
# int() is used for conversion
res = [tuple(int(ele) for ele in sub.split(K)) for sub in test_list]

# printing result
print("The converted tuple list : " + str(res))
```

**Output**

```py
The original list is : ['1-2', '3-4-8-9', '4-10-4']
The converted tuple list : [(1, 2), (3, 4, 8, 9), (4, 10, 4)]

```

**方法二:使用 map() + split() +列表理解**

在这种情况下，使用 [map()](https://www.geeksforgeeks.org/python-map-function/) 完成积分扩展逻辑的扩展任务，然后使用列表理解来执行列表的构建任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert K delim Strings to Integer Tuple List
# Using map() + split() + list comprehension

# initializing list
test_list = ["1-2", "3-4-8-9", "4-10-4"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = "-"

# extension logic using map()
# int() is used for conversion
res = [tuple(map(int, sub.split(K))) for sub in test_list]

# printing result
print("The converted tuple list : " + str(res))
```

**Output**

```py
The original list is : ['1-2', '3-4-8-9', '4-10-4']
The converted tuple list : [(1, 2), (3, 4, 8, 9), (4, 10, 4)]

```