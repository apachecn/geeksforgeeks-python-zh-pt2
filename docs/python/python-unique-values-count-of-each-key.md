# Python–每个键的唯一值计数

> 原文:[https://www . geesforgeks . org/python-唯一值-每个键的计数/](https://www.geeksforgeeks.org/python-unique-values-count-of-each-key/)

给定一个字典列表，任务是编写一个 Python 程序来计算每个键的唯一值。

**示例:**

> **输入:**test _ list =[{“gfg”:1，“是”:3，“最佳”:2}，{“gfg”:1，“是”:3，“最佳”:6}，
> 
> {“gfg”:7，“is”:3，“best”:10 }]
> 
> **输出:** {'gfg': 2，' is': 1，' best': 3}
> 
> **说明:** gfg 有 1 和 7 作为唯一元素，因此有 2。
> 
> **输入:**test _ list =[{“gfg”:1，“是”:3，“最佳”:2}，{“gfg”:1，“是”:3，“最佳”:6}，
> 
> {“gfg”:1，“is”:3，“best”:10 }]
> 
> **输出:** {'gfg': 1，' is': 1，' best': 3}
> 
> **说明:** gfg 只有 1 作为唯一元素，因此为 1。

**方法#1:使用**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**set()**](https://www.geeksforgeeks.org/python-set-method/)**+loop**

在这种情况下，使用 set()提取唯一值，使用 len()获取其计数，然后将结果映射到使用 key()提取的每个键。循环中出现对键的迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Unique values count of each Key
# Using len() + set()

# initializing lists
test_list = [{"gfg": 1, "is": 3, "best": 2}, {
    "gfg": 1, "is": 3, "best": 6}, {"gfg": 7, "is": 3, "best": 10}]

# printing original list
print("The original list is : " + str(test_list))

res = dict()
for key in test_list[0].keys():

    # mapping unique values.
    res[key] = len(set([sub[key] for sub in test_list]))

# printing result
print("Unique count of keys : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 1，' is': 3，' best': 2}，{'gfg': 1，' is': 3，' best': 6}，
> 
> {'gfg': 7，' is': 3，' best': 10}]
> 
> 唯一键计数:{“gfg”:2，“is”:1，“best”:3 }

**方法二:利用字典理解+ len() +** [**集合()**](https://www.geeksforgeeks.org/python-set-method/)

与上述方法类似，区别在于字典理解被用作速记的一种线性替代方法。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Unique values count of each Key
# Using len() + set() + dictionary comprehension

# initializing lists
test_list = [{"gfg": 1, "is": 3, "best": 2}, {
    "gfg": 1, "is": 3, "best": 6}, {"gfg": 7, "is": 3, "best": 10}]

# printing original list
print("The original list is : " + str(test_list))

# dictionary comprehension for compact solution
res = {key: len(set([sub[key] for sub in test_list]))
       for key in test_list[0].keys()}

# printing result
print("Unique count of keys : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 1，' is': 3，' best': 2}，{'gfg': 1，' is': 3，' best': 6}，
> 
> {'gfg': 7，' is': 3，' best': 10}]
> 
> 唯一键计数:{“gfg”:2，“is”:1，“best”:3 }