# Python |从列表中移除无序的重复元素

> 原文:[https://www . geesforgeks . org/python-remove-无序-重复-元素-从列表中删除/](https://www.geeksforgeeks.org/python-remove-unordered-duplicate-elements-from-a-list/)

给定一个列表，任务是删除重复的元素。所有顺序不同但由相同字符/数字组成的元素都被视为重复元素。

**示例:**

```
Input : ['gfg', 'ggf', 'fgg', 'for', 'orf',
                'ofr', 'rfo', 'rof', 'fro']
Output : ['for', 'fgg']

Input:  ['110', '101', '001', '010', '100']
Output:  ['001', '011']
```

**方法#1 :** 使用*设置*

```
# Python code to remove duplicate 
# unordered elements from a list
from collections import Counter

# List initialisation
Input = ['1213','1231','1123','1132','2113',
         '2311','0007', '0016', '0025', '0034',
         '0043', '0052', '0061', '0070','0304',
         '0313', '0322','0098','9800', '0331',
         '0340', '0403', '0412', '0421', '0430',
         '0502','8900','8009' ,'0511', '0520',
         '0601', '0610', '0700', '1006', '1015']

# Set initialisation
s = set()

# Output list initialisation
output =[]

for i in Input:
    if tuple(Counter(sorted(i, key = int)).items()) in s:
        pass

    else:
        s.add(tuple(Counter(sorted(i, key = int)).items()))
        output.append(i)

# Printing output
print(output)
```

**Output:**

```
['1213', '0007', '0016', '0025', '0034', 
 '0313', '0322', '0098', '0412', '0511']

```

**方法 2 :**

```
# Python code to remove duplicate
# unordered elements from a list
# List initialisation
Input = ['gfg', 'ggf', 'fgg', 'for', 'orf',
                'ofr', 'rfo', 'rof', 'fro']

# Getting unique nos
Output = list({''.join(sorted(n)) for n in Input})

# Printing Output
print(Output)
```

**Output:**

```
['for', 'fgg']

```