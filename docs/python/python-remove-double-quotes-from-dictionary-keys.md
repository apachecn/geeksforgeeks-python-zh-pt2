# Python–从字典键中删除双引号

> 原文:[https://www . geeksforgeeks . org/python-remove-双引号-从字典-键/](https://www.geeksforgeeks.org/python-remove-double-quotes-from-dictionary-keys/)

给定带有字符串键的字典，去掉双引号。

> **输入**:test _ dict = {“‘极客’”:3、“‘g’eeks”:9 }
> **输出**:{“‘极客’:3、‘极客’:9 }
> **解释**:按键去掉双引号。
> 
> **输入**:test _ dict = {“‘极客’”:3 }
> **输出**:{“‘极客’:3 }
> **解释**:按键去掉双引号。

**方法一:使用词典理解+替换()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用带有空字符串的 replace()来删除双引号。字典理解用于重造字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove double quotes from dictionary keys
# Using dictionary comprehension + replace()

# initializing dictionary
test_dict = {'"Geeks"' : 3, '"is" for' : 5, '"g"eeks' : 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# dictionary comprehension to make double quotes free
# dictionary
res = {key.replace('"', ''):val for key, val in test_dict.items()}

# printing result
print("The dictionary after removal of double quotes : " + str(res))
```

**Output**

```py
The original dictionary is : {'"Geeks"': 3, '"is" for': 5, '"g"eeks': 9}
The dictionary after removal of double quotes : {'Geeks': 3, 'is for': 5, 'geeks': 9}
```

**方法二:使用 re.sub() +词典理解**

上述功能的组合也是解决这一任务的替代方案。在这种情况下，我们使用正则表达式来解决这个问题。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove double quotes from dictionary keys
# Using re.sub() + dictionary comprehension
import re

# initializing dictionary
test_dict = {'"Geeks"' : 3, '"is" for' : 5, '"g"eeks' : 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# regex making replacement of double quotes with empty string
res = {re.sub(r'"', '', key): val for key, val in test_dict.items()}

# printing result
print("The dictionary after removal of double quotes : " + str(res))
```

**Output**

```py
The original dictionary is : {'"Geeks"': 3, '"is" for': 5, '"g"eeks': 9}
The dictionary after removal of double quotes : {'Geeks': 3, 'is for': 5, 'geeks': 9}
```