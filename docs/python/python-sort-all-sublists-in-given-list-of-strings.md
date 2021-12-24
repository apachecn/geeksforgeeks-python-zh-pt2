# Python |对给定字符串列表中的所有子列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-all-sublist-in-给定字符串列表/](https://www.geeksforgeeks.org/python-sort-all-sublists-in-given-list-of-strings/)

给定列表列表，任务是对给定字符串列表中的每个子列表进行排序。

**示例:**

```py
Input:
lst = [['Machine', 'London', 'Canada', 'France'],
       ['Spain', 'Munich'],
       ['Australia', 'Mandi']]

Output:
flist = [['Canada', 'France', 'London', 'Machine'],
         ['Munich', 'Spain'],
         ['Australia', 'Mandi']]

```

有多种方法可以按字母顺序对每个列表进行排序。

**方法#1:使用地图**

```py
# Python code  to sort all sublists 
# in given list of strings

# List initialization
Input = [['Machine', 'London', 'Canada', 'France', 'Lanka'],
         ['Spain', 'Munich'],
         ['Australia', 'Mandi']]

# Using map for sorting
Output = list(map(sorted, Input))

# Printing output
print(Output)
```

**Output:**

> ['加拿大'，'法国'，'斯里兰卡'，'伦敦'，'机器'，['慕尼黑'，'西班牙'，['澳大利亚'，'曼迪']]

**方法 2:使用λ并排序**

```py
# Python code  to sort all sublists
# in given list of strings

# List initialization
Input = [['Machine', 'London', 'Canada', 'France', 'Lanka'],
         ['Spain', 'Munich'],
         ['Australia', 'Mandi']]

# using lambda and sorted
Output = [sorted(x, key = lambda x:x[0]) for x in Input]

# Printing output
print(Output)
```

**Output:**

> ['加拿大'，'法国'，'伦敦'，'斯里兰卡'，'机器'，['慕尼黑'，'西班牙'，['澳大利亚'，'曼迪']]

**方法#3:使用迭代和排序**

```py
# Python code  to sort all sublists
# in given list of strings

# List initialization
Input = [['Machine', 'London', 'Canada', 'France', 'Lanka'],
         ['Spain', 'Munich'],
         ['Australia', 'Mandi']]

# sorting sublist
for sublist in Input:
    sublist.sort()

# Printing output
print(Input)
```

**Output:**

> ['加拿大'，'法国'，'斯里兰卡'，'伦敦'，'机器'，['慕尼黑'，'西班牙'，['澳大利亚'，'曼迪']]