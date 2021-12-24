# Python–使用重复键合并字典列表

> 原文:[https://www . geesforgeks . org/python-merge-dictionary-list-with-replicate-key/](https://www.geeksforgeeks.org/python-merge-dictionaries-list-with-duplicate-keys/)

给定两个可能有重复键的字典列表，编写一个 Python 程序来执行合并。

**示例:**

> **输入**:test _ list 1 =[{“gfg”:1，“最佳”:4}、{“极客”:10、“好”:15}、{“爱”:“gfg”}]、test _ list 2 =[{“gfg”:6 }、{“更好”:3、“适合”:10、“极客”:1}、{“gfg”:10 }]
> **输出**:[{“gfg”:1、“最佳”:4}、{“极客”:10、“好”:10
> 
> **输入**:test _ list 1 =[{“gfg”:1，“best”:4 }，{“love”:“gfg”}]，test _ list 2 =[{“gfg”:6 }，{“gfg”:10 }]
> **输出**:[{“gfg”:1，“best”:4 }，{“love”:“gfg”，“gfg”:10 }]
> **解释** : gfg 在合并的同时保留值 1，字典中加入“best”

**进场:使用回环+** [**键()**](https://www.geeksforgeeks.org/python-dictionary-keys-method/)

在这种情况下，我们根据所有不重复出现的键重建键值对，使用 In 运算符进行检查，并使用 key()提取键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Merge Dictionaries List with duplicate Keys
# Using loop + keys()

# initializing lists
test_list1 = [{"gfg": 1, "best": 4}, {"geeks": 10, "good": 15},
              {"love": "gfg"}]

test_list2 = [{"gfg": 6}, {"better": 3, "for": 10, "geeks": 1},
              {"gfg": 10}]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

for idx in range(0, len(test_list1)):

    # getting keys of corresponding index
    id_keys = list(test_list1[idx].keys())
    for key in test_list2[idx]:

        # checking for keys presence
        if key not in id_keys:
            test_list1[idx][key] = test_list2[idx][key]

# printing result
print("The Merged Dictionary list : " + str(test_list1))
```

**输出:**

> 原列表 1 为:[{'gfg': 1，' best': 4}，{'geeks': 10，' good': 15}，{'love': 'gfg'}]
> 原列表 2 为:[{'gfg': 6}，{'better': 3，' for': 10，' geeks': 1}，{'gfg': 10}]
> 合并词典列表:[{'gfg': 1，' best': 4}，{'geeks': 10，' good': 15，' better': 3，' for