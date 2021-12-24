# Python–用字典列表

中的第 k 个索引值替换值

> 原文:[https://www . geesforgeks . org/python-按 kth-index-value-in-dictionary-list/](https://www.geeksforgeeks.org/python-replace-value-by-kth-index-value-in-dictionary-list/)

给定一个字典列表，任务是编写一个 Python 程序，如果某个键的值是 list，则用第 k 个值索引替换该键的值。

**示例:**

> **输入** : test_list = [{'gfg' : [5，7，9，1]，' is' : 8，' good' : 10}，{'gfg' : 1，' for' : 10，' geeks' : 9}，{'love' : 3，' gfg' : [7，3，9，1]}]，K = 2，key = "gfg"
> **输出** : [{'gfg': 9，' is': 8，' good': 10}，{'gfg': 1，' for ':11
> 
> **输入** : test_list = [{'gfg' : [5，7，9，1]，' is' : 8，' good' : 10}，{'gfg' : 1，' for' : 10，'极客':9}]，K = 2，key = ' gfg "
> **输出** : [{'gfg': 9，' is': 8，' good': 10}，{'gfg': 1，' for': 10，'极客':9}]
> **解释** : gfg

**方法#1:使用 loop+**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)

在本文中，我们使用 isinstance()来检查值的列表类型，并使用循环来遍历字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace value by Kth index value in Dictionary List
# Using loop + isinstance()

# initializing list
test_list = [{'gfg': [5, 7, 9, 1], 'is': 8, 'good': 10},
             {'gfg': 1, 'for': 10, 'geeks': 9},
             {'love': 3, 'gfg': [7, 3, 9, 1]}]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# initializing Key
key = "gfg"

for sub in test_list:

    # using isinstance() to check for list
    if isinstance(sub[key], list):
        sub[key] = sub[key][K]

# printing result
print("The Modified Dictionaries : " + str(test_list))
```

**输出:**

> 原始列表为:[{'gfg': [5，7，9，1]，' is': 8，' good': 10}，{'gfg': 1，' for': 10，'极客':9}，{'love': 3，' gfg': [7，3，9，1]}]
> 修改后的词典:[{'gfg': 9，' is': 8，' good': 10}，{'gfg': 1，' for': 10，'极客':9}，{'love': 3，' gfg': 9}]

**方法二:使用** [**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)**+**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)

在本文中，我们使用 isinstance()用修改后的字典值重建字典，并使用字典理解来形成中间字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace value by Kth index value in Dictionary List
# Using dictionary comprehension + isinstance()

# initializing list
test_list = [{'gfg': [5, 7, 9, 1], 'is': 8, 'good': 10},
             {'gfg': 1, 'for': 10, 'geeks': 9},
             {'love': 3, 'gfg': [7, 3, 9, 1]}]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# initializing Key
key = "gfg"

# intermediate Dictionaries constructed using dictionary comprehension
res = [{newkey: (val[K] if isinstance(val, list) and newkey == key else val)
        for newkey, val in sub.items()} for sub in test_list]

# printing result
print("The Modified Dictionaries : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': [5，7，9，1]，' is': 8，' good': 10}，{'gfg': 1，' for': 10，'极客':9}，{'love': 3，' gfg': [7，3，9，1]}]
> 修改后的词典:[{'gfg': 9，' is': 8，' good': 10}，{'gfg': 1，' for': 10，'极客':9}，{'love': 3，' gfg': 9}]