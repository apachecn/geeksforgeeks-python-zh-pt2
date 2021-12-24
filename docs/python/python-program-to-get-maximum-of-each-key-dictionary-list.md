# Python 程序获取每个键的最大字典列表

> 原文:[https://www . geesforgeks . org/python-program-to-get-max-of-key-dictionary-list/](https://www.geeksforgeeks.org/python-program-to-get-maximum-of-each-key-dictionary-list/)

给定字典列表，编写一个 Python 程序来获取每个键的最大值。

**示例:**

> **输入**:test _ list =[{“Gfg”:8，“is”:1、“Best”:9 }、{“Gfg”:2、“is”:9、“Best”:1 }、{“Gfg”:5、“is”:10、“Best”:7 }]
> **输出**:{“Gfg”:8、“is”:10、“Best”:9 }
> **说明**:在可能的 8、2、5 中，Gfg 键的最大值为 8。
> 
> **输入**:test _ list =[{“Gfg”:8，“is”:1、“Best”:9 }、{“Gfg”:5、“is”:10、“Best”:7 }]
> **输出**:{“Gfg”:8、“is”:10、“Best”:9 }
> **解释**:Best 键的最大值在可能的 9、7 中为 7。

**方法#1:使用** [**物品()**](https://www.geeksforgeeks.org/python-dictionary-items-method/) **+循环+** [**max()**](https://www.geeksforgeeks.org/python-max-function/)

在这种情况下，我们使用循环迭代每个字典和其中的键，并使用 [max()](https://www.geeksforgeeks.org/python-max-function/) 不断更新每个键的最大值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# All Keys Maximum in Dictionary List
# Using items() + loop + max()

# initializing Matrix
test_list = [{"Gfg": 8, "is": 1, "Best": 9},
             {"Gfg": 2, "is": 9, "Best": 1},
             {"Gfg": 5, "is": 10, "Best": 7}]

# printing original list
print("The original list is : " + str(test_list))

res = {}
for dic in test_list:
    for key, val in dic.items():

        # checking for key presence and updating max
        if key in res:
            res[key] = max(res[key], val)
        else:
            res[key] = val

# printing result
print("All keys maximum : " + str(res))
```

**输出:**

> 原始列表为:[{'Gfg': 8，' is': 1，' Best': 9}，{'Gfg': 2，' is': 9，' Best': 1}，
> {'Gfg': 5，' is': 10，' Best': 7}]
> 所有键最大值:{'Gfg': 8，' Best': 9}原始列表为:[{'Gfg': 8，' is': 1，' Best': 9}，
> {'Gfg': 2，' is': 9，' Best': 1}，{'Gfg '

**方法 2:使用**[**default dict()**](https://www.geeksforgeeks.org/defaultdict-in-python/)

在这种情况下，我们省略了使用 defaultdict()对密钥存在性进行条件检查的步骤。其余所有功能与上述方法相似。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# All Keys Maximum in Dictionary List
# Using defaultdict()
from collections import defaultdict

# initializing Matrix
test_list = [{"Gfg": 8, "is": 1, "Best": 9},
             {"Gfg": 2, "is": 9, "Best": 1},
             {"Gfg": 5, "is": 10, "Best": 7}]

# printing original list
print("The original list is : " + str(test_list))

res = defaultdict(int)
for dic in test_list:
    for key, val in dic.items():

        # defaultdict helps to avoid conditional check here
        res[key] = max(res[key], val)

# printing result
print("All keys maximum : " + str(dict(res)))
```

**输出:**

> 原始列表为:[{'Gfg': 8，' is': 1，' Best': 9}，{'Gfg': 2，' is': 9，' Best': 1}，
> {'Gfg': 5，' is': 10，' Best': 7}]
> 所有键最大值:{'Gfg': 8，' is': 10，' Best': 9}