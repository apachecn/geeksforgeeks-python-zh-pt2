# 将矩阵转换为字典列表的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-转换-矩阵-字典列表/](https://www.geeksforgeeks.org/python-program-to-convert-matrix-to-list-of-dictionaries/)

给定一个矩阵，通过映射相似的索引值将其转换为字典列表。

> **输入** : test_list = [["Gfg "，[1，2，3]]，["best "，[9，10，11]]
> **输出** : [{'Gfg': 1，' best': 9}，{'Gfg': 2，' best': 10}，{'Gfg': 3，' best': 11}]
> 
> **输入**:test _ list =[[“Gfg”，[1，2，3]]
> **输出** : [{'Gfg': 1}，{'Gfg': 2}，{'Gfg': 3}]

执行这项任务的暴力方式是使用循环。在这种情况下，我们迭代矩阵中的所有元素，并更新字典，将键绑定到字典中的适当值。

## 蟒蛇 3

```py
# initializing list
test_list = [["Gfg", [1, 2, 3]],
             ["is", [6, 5, 4]], ["best", [9, 10, 11]]]

# printing original list
print("The original list : " + str(test_list))

# using loop to bind Matrix elements to dictionary
res = []
for key, val in test_list:

    for idx, val in enumerate(val):

        # append values according to rows structure
        if len(res) - 1 < idx:
            res.append({key: val})

        else:
            res[idx].update({key: val})

# printing result
print("Converted dictionary : " + str(res))
```

**输出:**

> 原始列表:[[[' Gfg '，[1，2，3]]，['is '，[6，5，4]]，['best '，[9，10，11]]
> 转换词典:[{'Gfg': 1，' is': 6，' best': 9}，{'Gfg': 2，' is': 5，' best': 10}，{'Gfg': 3，' is': 4，' best': 11}]