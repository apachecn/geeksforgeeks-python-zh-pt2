# Python–在字符串中的索引处替换为 K

> 原文:[https://www . geesforgeks . org/python-replace-to-k-at-with-index-in-string/](https://www.geeksforgeeks.org/python-replace-to-k-at-ith-index-in-string/)

给定一个字符串，用 K 值替换索引。

> **输入** : test_str = 'geeks5geeks '，K = '7 '，i = 5
> **输出** : 'geeks7geeks'
> **解释**:元素为 5，用索引转换为 7。
> 
> **输入** : test_str = 'geeks5geeks '，K = '7 '，i = 6
> **输出** : 'geeks56eeks'
> **解释**:元素为 g，用索引转换为 7。

**方法#1:使用串切片**

在这种情况下，我们使用字符串切片方法对前字符串进行切片，直到 I，然后添加 K，然后添加后值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Replace to K at ith Index in String
# using string slicing

# initializing strings
test_str = 'geeks5geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = '4'

# initializing i
i = 5

# the replaced result 
res = test_str[: i] + K + test_str[i + 1:]

# printing result 
print("The constructed string : " + str(res)) 
```

**Output**

```py
The original string is : geeks5geeks
The constructed string : geeks4geeks

```

**方法 2:使用 join() +生成器表达式**

在本文中，我们使用生成器表达式执行检查索引和有条件追加 K 的任务，并使用 join()将结果转换为字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Replace to K at ith Index in String
# using join() + generator expression

# initializing strings
test_str = 'geeks5geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = '4'

# initializing i
i = 5

# the replaced result 
res = ''.join(test_str[idx] if idx != i else K for idx in range(len(test_str)))

# printing result 
print("The constructed string : " + str(res)) 
```

**Output**

```py
The original string is : geeks5geeks
The constructed string : geeks4geeks

```