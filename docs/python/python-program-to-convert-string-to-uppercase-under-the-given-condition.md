# 给定条件下将字符串转换为大写的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-convert-string-to-大写-在给定条件下/](https://www.geeksforgeeks.org/python-program-to-convert-string-to-uppercase-under-the-given-condition/)

给定一个字符串列表，任务是编写一个 Python 程序来转换长度大于 k 的大写字符串

**示例:**

> **输入:**test _ list =[“Gfg”、“is”、“best”、“for”、“geeks”]，K = 3
> 
> **输出:** ['Gfg '，' is '，' BEST '，' for '，' GEEKS']
> 
> **说明:** Best 有 4 个字符，因此 Best 是大写的。
> 
> **输入:**test _ list =[“Gfg”、“is”、“best”、“for”、“geeks”]，K = 4
> 
> **输出:** ['Gfg '，' is '，' best '，' for '，' GEEKS']
> 
> **说明:**极客有 5 个字符[大于 4]，因此极客是大写的。

**方法#1:使用** [**上位()**](https://www.geeksforgeeks.org/python-string-upper/) **+** [**循环**](https://www.geeksforgeeks.org/python-for-loops/)

在这种情况下，我们使用 upper()执行 uppercasing 任务，并且使用 loop 检查更大的条件语句。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Conditional Uppercase by size
# Using upper() + loop

# initializing list
test_list = ["Gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

res = []
for ele in test_list:

    # check for size
    if len(ele) > K:
        res.append(ele.upper())
    else:
        res.append(ele)

# printing result
print("Modified Strings : " + str(res))
```

**输出:**

```
The original list is : ['Gfg', 'is', 'best', 'for', 'geeks']
Modified Strings : ['Gfg', 'is', 'BEST', 'for', 'GEEKS']
```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，迭代任务是在列表理解中执行的，作为上面类似方法的简写。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Conditional Uppercase by size
# Using list comprehension

# initializing list
test_list = ["Gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# list comprehension for one liner solution
res = [ele.upper() if len(ele) > K else ele for ele in test_list]

# printing result
print("Modified Strings : " + str(res))
```

**输出:**

```
The original list is : ['Gfg', 'is', 'best', 'for', 'geeks']
Modified Strings : ['Gfg', 'is', 'BEST', 'for', 'GEEKS']
```