# Python 程序将字典及其键划分为 K 个相等的字典

> 原文:[https://www . geesforgeks . org/python-程序-将字典及其键划分为 k 个相等的字典/](https://www.geeksforgeeks.org/python-program-to-divide-dictionary-and-its-keys-into-k-equal-dictionaries/)

给定一个字典，通过划分每个键的值，将其划分为大小为 k 的相等字典列表。

> **输入**:test _ dict = {“Gfg”:9、“is”:6、“best”:12 }、K = 3
> **输出**:[{“Gfg”:3.0、“is”:2.0、“best”:4.0 }、{“Gfg”:3.0、“is”:2.0、“best”:4.0 }、{“Gfg”:3.0、“is”:2.0、“best”:4.0 }]
> **解释**:值在字典中平均分布。
> 
> **输入**:test _ dict = {“Gfg”:6、“is”:4、“best”:2 }、K = 2
> **输出**:[{“Gfg”:3.0、“is”:2.0、“best”:1.0 }、{“Gfg”:3.0、“is”:2.0、“best”:1.0 }]
> **解释**:值在字典中平均分布。

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们计算每个必需键的值，并将每个字典追加到字典列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Divide dictionary into K equal dictionaries
# Using loop

# initializing dictionary
test_dict = {"Gfg": 20, "is": 36, "best": 100}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing size
K = 4

# constructing new dict
temp = dict()
for key in test_dict:
    temp[key] = test_dict[key] / 4

# creating list
res = []
for idx in range(K):
    res.append(temp)

# printing result
print("Required dictionary list : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': 20，' is': 36，' best': 100}
> 必选词典列表:[{'Gfg': 5.0，' is': 9.0，' best': 25.0}，{'Gfg': 5.0，' is': 9.0，' is': 9.0，' best': 25.0}，{'Gfg': 5.0，' is': 9.0，' best': 25.0}]

**方法二:使用词典理解+列表理解**

这是执行这项任务的另一种方式。在这篇文章中，我们使用字典理解形成字典，使用列表理解作为解决这个问题的速记。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Divide dictionary into K equal dictionaries
# Using dictionary comprehension + list comprehension

# function to divide dictionary
# and keys into K equal dictionaries
def divideDictKeys(dictionary, K):

    # constructing new dict
    # using dictionary comprehension
    temp = {key: test_dict[key] / K for key in test_dict}

    # creating list
    # using list comprehension
    res = [temp for idx in range(K)]

    return str(res)

# driver code

# initializing dictionary
test_dict = {"Gfg": 20, "is": 36, "best": 100}

# initializing size
K = 4

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# printing result
print("Required dictionary list : " + divideDictKeys(test_dict, K))
```

**输出:**

> 原词典为:{'Gfg': 20，' is': 36，' best': 100}
> 必选词典列表:[{'Gfg': 5.0，' is': 9.0，' best': 25.0}，{'Gfg': 5.0，' is': 9.0，' is': 9.0，' best': 25.0}，{'Gfg': 5.0，' is': 9.0，' best': 25.0}]