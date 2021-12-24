# 将字典字符串值转换为字典列表的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-转换-字典-字符串-值-字典列表/](https://www.geeksforgeeks.org/python-program-to-convert-dictionary-string-values-to-list-of-dictionaries/)

给定一个以值作为分隔符分隔值的字典，任务是编写一个 python 程序，将字典列表中的每个字符串转换为不同的值。

> **输入**:test _ dict = {“Gfg”:“1:2:3”，“best”:“4:8:11”}
> **输出**:[{“Gfg”:“1”，“best”:“4”}，{“Gfg”:“2”，“best”:“8”}，{“Gfg”:“3”，“best”:“11”}]
> **解释**:字典值拆分后列表。
> 
> **输入**:test _ dict = {“Gfg”:“1:2:3”}
> **输出**:[{“Gfg”:“1”}，{“Gfg”:“2”}，{“Gfg”:“3”}]
> **解释**:字典值拆分后列表。

**方法:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*分割()*](https://www.geeksforgeeks.org/python-string-split/)

上述功能的组合可以用来解决这个问题。在这种情况下，我们对每个键的值进行拆分，并在字典列表中将其呈现为单独的值。

**示例:**

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert dictionary string values to Dictionaries List
# Using loop
from collections import defaultdict

# initializing dictionary
test_dict = {"Gfg": "1:2:3:7:9", "best": "4:8", "good": "2"}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# create empty mesh
temp = defaultdict(dict)
for key in test_dict:

    # iterate for each of splitted values
    for idx in range(len(test_dict[key].split(':'))):
        try:
            temp[idx][key] = test_dict[key].split(':')[idx]

        # handle case with No value in split
        except Exception as e:
            temp[idx][key] = None

res = []
for key in temp:

    # converting nested dictionaries to list of dictionaries
    res.append(temp[key])

# printing result
print("Required dictionary list : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': '1:2:3:7:9 '，' best': '4:8 '，' good': '2'}
> 
> 必需的字典列表:[{'Gfg': '1 '，' best': '4 '，' good': '2'}，{'Gfg': '2 '，' best': '8'}，{'Gfg': '3'}，{'Gfg': '7'}，{'Gfg': '9'}]