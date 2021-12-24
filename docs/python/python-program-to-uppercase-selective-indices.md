# Python 程序到大写选择索引

> 原文:[https://www . geesforgeks . org/python-程序到大写字母的选择性索引/](https://www.geeksforgeeks.org/python-program-to-uppercase-selective-indices/)

给定字符串，对特定索引执行大写。

> **输入**:test _ str = ' geeksgeeksisbestforkeks '，idx_list = [5，7，3，2，6，9]
> **输出**:geeksgeeksisbestforkeks
> **解释**:具体指标上调。
> 
> **输入**:test _ str = ' geeksgeeksisbestforgeks '，idx_list = [5，7，3]
> **输出**:geeksgeeksisbestforgeks
> **解释**:具体指标上调。

**方法#1:使用 loop +** [**上位()**](https://www.geeksforgeeks.org/python-string-upper/)

在本例中，我们使用 upper()执行转换为大写的任务，并从列表中转换为大写的检查索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Uppercase selective indices
# Using loop + upper()

# initializing string
test_str = 'geeksgeeksisbestforgeeks' 

# printing original string
print("The original string is : " + str(test_str))

# initializing indices list 
idx_list = [5, 7, 3, 2, 6, 9]

res = ''
for idx in range(0, len(test_str)):

    # checking for index list for uppercase 
    if idx in idx_list:
        res += test_str[idx].upper()
    else:
        res += test_str[idx]

# printing result 
print("Transformed String : " + str(res)) 
```

**Output**

```py
The original string is : geeksgeeksisbestforgeeks
Transformed String : geEKsGEEkSisbestforgeeks

```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**上位()**](https://www.geeksforgeeks.org/python-string-upper/) **+** [**加入()**](https://www.geeksforgeeks.org/join-function-python/)

类似于上面的方法，区别是列表理解用于提供一个 liner，join()用于转换回字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Uppercase selective indices
# Using list comprehension + upper() + join()

# initializing string
test_str = 'geeksgeeksisbestforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing indices list
idx_list = [5, 7, 3, 2, 6, 9]

# one-liner way to solve this problem
res = ''.join([test_str[idx].upper() if idx in idx_list else test_str[idx]
               for idx in range(0, len(test_str))])

# printing result
print("Transformed String : " + str(res))
```

**Output**

```py
The original string is : geeksgeeksisbestforgeeks
Transformed String : geEKsGEEkSisbestforgeeks

```