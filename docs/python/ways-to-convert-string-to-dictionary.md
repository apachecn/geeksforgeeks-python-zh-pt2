# 字符串到字典的转换方式

> 原文:[https://www . geesforgeks . org/将字符串转换为字典的方法/](https://www.geeksforgeeks.org/ways-to-convert-string-to-dictionary/)

[字典](https://www.geeksforgeeks.org/python-dictionary/)是 Python 中的无序集合，它像地图一样存储数据值，即`key:value`对。为了将字符串转换为字典，存储的字符串必须能够从中生成`key:value`对。本文演示了几种将字符串转换成字典的方法。

**方法 1:拆分字符串以生成字典**
的`key:value`对在这种方法中，给定的字符串将被分析，并且使用`[split()](https://www.geeksforgeeks.org/python-string-split/)`方法，字符串将以生成用于创建字典的`key:value`对的方式被拆分。

下面是该方法的实现。

```py
# Python implementation of converting
# a string into a dictionary

# initialising string 
str = " Jan = January; Feb = February; Mar = March"

# At first the string will be splitted
# at the occurence of ';' to divide items 
# for the dictionaryand then again splitting 
# will be done at occurence of '=' which
# generates key:value pair for each item
dictionary = dict(subString.split("=") for subString in str.split(";"))

# printing the generated dictionary
print(dictionary)
```

**Output:**

```py
{' Feb ': ' February', ' Mar ': ' March', ' Jan ': ' January'}

```

**方法 2:使用 2 个字符串为字典**
生成`key:value`对在这种方法中，将考虑 2 个不同的字符串，其中一个用于生成关键字，另一个用于为字典生成值。操纵这两个字符串后，将使用那些`key:value`对创建字典项目。

下面是该方法的实现。

```py
# Python implementation of converting
# a string into a dictionary

# initialising first string
str1 = "Jan, Feb, March"
str2 = "January | February | March"

# splitting first string
# in order to get keys
keys = str1.split(", ")

# splitting second string
# in order to get values
values = str2.split("|")

# declaring the dictionary
dictionary = {}

# Assigning keys and its 
# corresponding values in
# the dictionary
for i in range(len(keys)):
    dictionary[keys[i]] = values[i]

# printing the generated dictionary
print(dictionary)
```

**Output:**

```py
{'Jan': 'January ', 'Feb': ' February ', 'March': ' March'}

```

**方法 3:使用`zip()`方法组合从 2 个字符串**
中提取的`key:value`对。在这种方法中，将再次使用 2 个字符串，一个用于生成关键字，另一个用于为字典生成值。当所有的键和值都被存储后，将使用`[zip()](https://www.geeksforgeeks.org/zip-in-python/)`方法创建`key:value`对，从而生成完整的字典。

下面是该方法的实现。

```py
# Python implementation of converting
# a string into  a dictionary

# initialising first string
str1 = "Jan, Feb, March"
str2 = "January | February | March"

# splitting first string
# in order to get keys
keys = str1.split(", ")

# splitting second string
# in order to get values
values = str2.split("|")

# declaring the dictionary
dictionary = {}

# Merging all keys and values
# to generate items for
# the dictionary
dictionary = dict(zip(keys, values))

# printing the generated dictionary
print(dictionary)
```

**Output:**

```py
{' March': ' March', 'Jan': 'January ', ' Feb': ' February '}

```

**方法 4:如果字符串本身是字符串字典的形式**
在这种方法中，已经是字符串字典形式的字符串，即**字符串有字典表达式**使用`ast.literal_eval()`方法转换成字典。

下面是该方法的实现。

```py
# Python implementation of converting
# a string into  a dictionary

# importing ast module
import ast 

# initialising string dictionary 
str = '{"Jan" : "January", "Feb" : "February", "Mar" : "March"}'

# converting string into dictionary
dictionary = ast.literal_eval(str)

# printing the generated dictionary
print(dictionary)
```

**Output:**

```py
{'Feb': 'February', 'Jan': 'January', 'Mar': 'March'}

```