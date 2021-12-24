# Python–字典列表中键的值限制

> 原文:[https://www . geeksforgeeks . org/python-字典中键的值限制-list/](https://www.geeksforgeeks.org/python-value-limits-to-keys-in-dictionaries-list/)

给定一个字典列表，编写一个 Python 程序给字典列表中的每个键分配限制。(每个都有所有键)。

**示例:**

> **输入**:test _ list =[{“gfg”:4、“is”:7、“best”:10 }、{“gfg”:2、“is”:5、“best”:9 }、{“gfg”:1、“is”:2、“best”:6 }]
> **输出**:{“gfg”:[1，4]、“‘is’:[2，7]、“‘best’:[6，10]}
> **解释** : gfg 有 min。值为 1，最大值为 4。
> 
> **输入**:test _ list =[{“gfg”:4，“best”:10 }、{“gfg”:2，“best”:9 }、{“gfg”:1，“best”:6 }]
> **输出**:{“gfg”:[1，4]、“‘best’:[6，10]}
> **解释** : best 有 min。值为 6，最大值为 10。

**方法#1:使用**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+**[**min()**](https://www.geeksforgeeks.org/python-min-function/)**+loop+**[**key()**](https://www.geeksforgeeks.org/python-dictionary-keys-method/)

在本例中，我们使用键()执行获取所有键的任务，并使用最小()和最大()计算极限的最小和最大值。所有字典的迭代都是使用循环进行的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Value limits to keys in Dictionaries List
# Using max() + min() + loop + keys()

# initializing Matrix
test_list = [{"gfg": 4, "is": 7, "best": 10},
             {"gfg": 2, "is": 5, "best": 9},
             {"gfg": 1, "is": 2, "best": 6}]

# printing original list
print("The original list is : " + str(test_list))

res = dict()

# extraction of all keys
keys = list(test_list[0].keys())

for key in keys:

    # assigning ranges to each key
    res[key] = [min(sub[key] for sub in test_list), max(sub[key]
                                                        for sub in test_list)]

# printing result
print("Keys Ranges : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 4，' is': 7，' best': 10}，{'gfg': 2，' is': 5，' best': 9}，{'gfg': 1，' is': 2，' best': 6}]
> 键范围:{'gfg': [1，4]，' is': [2，7]，' best': [6，10]}

**方法二:使用** [**字典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)**+min()+max()+**[**键()**](https://www.geeksforgeeks.org/python-dictionary-keys-method/)

在这种情况下，我们使用一个线性字典理解来执行迭代任务，与上面的方法类似，但是是一个简写。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Value limits to keys in Dictionaries List
# Using list comprehension + min() + max() + keys()

# initializing Matrix
test_list = [{"gfg": 4, "is": 7, "best": 10},
             {"gfg": 2, "is": 5, "best": 9},
             {"gfg": 1, "is": 2, "best": 6}]

# printing original list
print("The original list is : " + str(test_list))

# extraction of all keys
keys = list(test_list[0].keys())

# Dictionary comprehension used as one liner to perform task
res = {key: [min(sub[key] for sub in test_list), max(sub[key]
                                                     for sub in test_list)] for key in keys}

# printing result
print("Keys Ranges : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 4，' is': 7，' best': 10}，{'gfg': 2，' is': 5，' best': 9}，{'gfg': 1，' is': 2，' best': 6}]
> 键范围:{'gfg': [1，4]，' is': [2，7]，' best': [6，10]}