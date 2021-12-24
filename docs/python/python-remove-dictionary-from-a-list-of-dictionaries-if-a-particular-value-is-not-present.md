# Python–如果特定值不存在，则从字典列表中删除字典

> 原文:[https://www . geesforgeks . org/python-从字典列表中删除字典-如果特定值不存在/](https://www.geeksforgeeks.org/python-remove-dictionary-from-a-list-of-dictionaries-if-a-particular-value-is-not-present/)

给定一个字典列表，删除所有没有 K 值的字典。

**示例:**

> **输入**:test _ list =[{“Gfg”:4，“is”:8，“best”:9 }、{“Gfg”:3，“is”:7，“best”:5 }]、K = 7
> **输出**:[{“Gfg”:4，“is”:8，“best”:9 }]
> **解释**:结果字典不包含 7 作为任何元素。
> 
> **输入**:test _ List =[{“Gfg”:4、“is”:7、“best”:9 }、{“Gfg”:3、“is”:7、“best”:5 }]、K = 7
> **输出** : []
> **解释**:List 中均包含 7 作为元素。

**方法#1:使用循环+值()**

这是执行这项任务的方法之一。在本例中，我们使用循环执行迭代所有字典的任务，并使用值()检查值是否存在。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove dictionary if K value not present
# Using loop + values()

# initializing lists
test_list = [{"Gfg" : 4, "is" : 8, "best" : 9},
             {"Gfg" : 5, "is": 8, "best" : 1},
             {"Gfg" : 3, "is": 7, "best" : 6}, 
             {"Gfg" : 3, "is": 7, "best" : 5}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 7

res = []

# using loop to check for K element 
for sub in test_list:
    if K not in list(sub.values()):
        res.append(sub)

# printing result 
print("Filtered dictionaries : " + str(res))
```

**输出:**

> 原始列表:[{'Gfg': 4，' is': 8，' best': 9}，{'Gfg': 5，' is': 8，' best': 1}，{'Gfg': 3，' is': 7，' best': 6}，{'Gfg': 3，' is': 7，' best': 5}]
> 筛选词典:[{'Gfg': 4，' is': 8，' best': 9}，{'Gfg': 5，' is': 8，' best': 1}]

**方法 2:使用列表理解**

这是执行这项任务的另一种方式。在这种情况下，我们使用列表理解使用一行提取所有的值。这些值是使用值()提取的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove dictionary if K value not present
# Using list comprehension

# initializing lists
test_list = [{"Gfg" : 4, "is" : 8, "best" : 9},
             {"Gfg" : 5, "is": 8, "best" : 1},
             {"Gfg" : 3, "is": 7, "best" : 6}, 
             {"Gfg" : 3, "is": 7, "best" : 5}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 7

res = []

# using one-liner to extract dicts with NO K value
# using not in operator to check presence
res = [sub for sub in test_list if K not in list(sub.values())]

# printing result 
print("Filtered dictionaries : " + str(res))
```

**输出:**

> 原始列表:[{'Gfg': 4，' is': 8，' best': 9}，{'Gfg': 5，' is': 8，' best': 1}，{'Gfg': 3，' is': 7，' best': 6}，{'Gfg': 3，' is': 7，' best': 5}]
> 筛选词典:[{'Gfg': 4，' is': 8，' best': 9}，{'Gfg': 5，' is': 8，' best': 1}]