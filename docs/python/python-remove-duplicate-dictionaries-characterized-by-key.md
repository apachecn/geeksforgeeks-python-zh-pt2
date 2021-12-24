# Python–删除以关键字

为特征的重复词典

> 原文:[https://www . geeksforgeeks . org/python-remove-replicate-dictionary-featured-by-key/](https://www.geeksforgeeks.org/python-remove-duplicate-dictionaries-characterized-by-key/)

给定一个字典列表，删除所有与 K 键重复的字典。

> **输入**:test _ list =[{“Gfg”:6、“is”:9、“best”:10 }、{“Gfg”:8、“is”:11、“best”:10 }、{“Gfg”:2、“is”:16、“best”:10 }]、K =“best”
> **输出**:[{“Gfg”:6、“is”:9、“best”:10 }]
> **解释:**所有键都有 10 值，只保留第 1 条记录。
> 
> **输入**:test _ list =[{“Gfg”:6、“是”:9、“最佳”:10}、{“Gfg”:8、“是”:11、“最佳”:12}、{“Gfg”:2、“是”:16、“最佳”:15}]、K =“最佳”
> **输出**:[{“Gfg”:6、“是”:9、“最佳”:10}、{“Gfg”:8、“是”:11、“最佳”:12}、{“Gfg”:2、“是”

**方法:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们对每个字典进行迭代，并记住关键字，如果出现相似关键字的相同值，则在字典的结果列表中避免该字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove Duplicate Dictionaries characterized by Key
# Using loop

# initializing lists
test_list = [{"Gfg" : 6, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 2, "is" : 16, "best" : 10},
             {"Gfg" : 12, "is" : 1, "best" : 8},
             {"Gfg" : 22, "is" : 6, "best" : 8}]

# printing original list
print("The original list : " + str(test_list))

# initializing Key 
K = "best"

memo = set()
res = []
for sub in test_list:

    # testing for already present value
    if sub[K] not in memo:
        res.append(sub)

        # adding in memo if new value
        memo.add(sub[K])

# printing result 
print("The filtered list : " + str(res))
```

**Output**

> 原始列表:[{'Gfg': 6，' is': 9，' best': 10}，{'Gfg': 8，' is': 11，' best': 19}，{'Gfg': 2，' is': 16，' best': 10}，{'Gfg': 12，' is': 1，' best': 8}，{'Gfg': 22 '，is': 6，' best': 8}]
> 筛选后的列表:[{'Gfg': 6，' is': 9，' best': 10}，{'Gfg': 8，' is ':