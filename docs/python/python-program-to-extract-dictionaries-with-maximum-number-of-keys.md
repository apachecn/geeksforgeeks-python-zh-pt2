# Python 程序提取最大键数字典

> 原文:[https://www . geesforgeks . org/python-带最大键数的程序提取字典/](https://www.geeksforgeeks.org/python-program-to-extract-dictionaries-with-maximum-number-of-keys/)

给定一个字典列表，任务是编写一个 python 程序，以最大的键数提取字典。

> **输入** : test_list = [{'Gfg' : 1}，{'Gfg' : 1，' is' : 5，' best' : 4}，{'Gfg' : 2，' best' : 9}]
> 
> **输出** : {'Gfg' : 1，' is' : 5，' best' : 4}
> 
> **说明**:带 max 的字典。输出长度 3。
> 
> **输入:** test_list = [{'Gfg' : 1}，{'Gfg' : 2，' best' : 9}]
> 
> **输出:** {'Gfg' : 2，' best' : 9}
> 
> **说明:**最大值字典。输出长度 2。

**方法 1 :** *使用* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/) *和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们迭代所有的字典，并跟踪其键的数量，在每一步比较和更新最大值。

此方法仅显示找到的第一个具有最大元素数量的字典，即如果多个字典具有相同数量的元素，并且该数量是最大值，则仅显示第一个字典。

**示例:**

## 蟒蛇 3

```py
# initializing list
test_list = [{'Gfg': 1}, {'Gfg': 1, 'is': 5, 'best': 4}, {'Gfg': 2, 'best': 9}]

# printing original list
print("The original list is : " + str(test_list))

res = dict()
max_len = 0
for sub in test_list:

    # comparing and updating maximum dictionary acc. to length
    if len(sub) > max_len:
        res = sub
        max_len = len(sub)

# printing result
print("Dictionary with maximum keys  : " + str(res))
```

**输出:**

> 原始列表为:[{'Gfg': 1}，{'Gfg': 1，' is': 5，' best': 4}，{'Gfg': 2，' best': 9}]
> 
> 最大键数为{'Gfg': 1，' is': 5，' best': 4}的字典

**方法二:** *使用* [*max()*](https://www.geeksforgeeks.org/max-min-python/) *和* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们得到了字典列表中存在的最大键数长度。然后提取计算出最大长度的字典。此方法允许多个匹配关键字的结果。

**示例:**

## 蟒蛇 3

```py
# initializing list
test_list = [{'Gfg': 1}, {'Gfg': 1, 'is': 5, 'best': 4},
             {'Gfg': 2, 'best': 9, "book": 1}]

# printing original list
print("The original list is : " + str(test_list))

max_len = max(len(sub) for sub in test_list)
res = [sub for sub in test_list if len(sub) == max_len]

# printing result
print("Dictionary with maximum keys  : " + str(res))
```

**输出:**

> 原始列表为:[{'Gfg': 1}，{'Gfg': 1，' is': 5，' best': 4}，{'Gfg': 2，' best': 9，' book': 1}]
> 
> 最大键数为:[{'Gfg': 1，' is': 5，' best': 4}，{'Gfg': 2，' best': 9，' book': 1}]