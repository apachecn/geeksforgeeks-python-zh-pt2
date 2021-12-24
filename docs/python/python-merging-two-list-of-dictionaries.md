# Python |合并两个字典列表

> 原文:[https://www . geesforgeks . org/python-合并-两个字典列表/](https://www.geeksforgeeks.org/python-merging-two-list-of-dictionaries/)

给定两个字典列表，任务是根据某个值合并这两个字典列表。

**方法#1:** 使用`defaultdict` 和`extend` 基于 *school_id* 合并两个词典列表。

```py
# Python code to  merge two list of dictionaries 
# based on some value.

from collections import defaultdict

# List initialization
Input1 = [{'roll_no': ['123445', '1212'], 'school_id': 1},
          {'roll_no': ['HA-4848231'], 'school_id': 2}]

Input2 = [{'roll_no': ['473427'], 'school_id': 2},
          {'roll_no': ['092112'], 'school_id': 5}]

# Using defaultdict
temp = defaultdict(list) 

# Using extend
for elem in Input1:
    temp[elem['school_id']].extend(elem['roll_no'])

for elem in Input2:
    temp[elem['school_id']].extend(elem['roll_no'])

Output = [{"roll_no":y, "school_id":x} for x, y in temp.items()]

# printing
print(Output)
```

**输出:**

> [{'school_id': 1，' roll_no': ['123445 '，' 1212']}，{'school_id': 2，' roll_no': ['HA-4848231 '，' 473427']}，{'school_id': 5，' roll_no': ['092112']}]