# Python 程序从关键字出现在列表中的字典中找到最大值

> 原文:[https://www . geesforgeks . org/python-program-to-find-value-from-dictionary-with-key-present-in-list/](https://www.geeksforgeeks.org/python-program-to-find-maximum-value-from-dictionary-whose-key-is-present-in-the-list/)

给定一个包含字典关键字和字典的列表，从字典值中提取最大值，其关键字出现在列表中。

**示例:**

> **输入**:test _ dict = {“Gfg”:4、“is”:5、“best”:10、“for”:11、“极客”:3}、test _ list =[“Gfg”、“best”、“极客”]
> **输出** : 10
> **说明**:最大值为 11，但不在列表中，10 为关键最佳，也在列表中。
> 
> **输入**:test _ dict = {“Gfg”:4、“is”:5、“best”:10、“for”:11、“极客”:3}、test _ list =[“Gfg”、“best”、“极客”、“for”]
> **输出** : 11
> **解释** : Max。值 11 也出现在列表中。

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们检查列表中的所有键以及最大值，然后返回最大可用值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Maximum value from List keys
# Using loop 

# initializing dictionary
test_dict = {"Gfg": 4, "is" : 5, "best" : 9,
             "for" : 11, "geeks" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing list 
test_list = ["Gfg", "best", "geeks"]

res = 0
for ele in test_list:

    # checking for key in dictionary
    if ele in test_dict:
        res = max(res, test_dict[ele])

# printing result 
print("The required maximum : " + str(res)) 
```

**输出:**

> 最初的字典是:{'Gfg': 4，' is': 5，' best': 9，' for': 11，' geeks': 3}
> 要求的最大值:9

**方法二:使用 max() +列表理解**

这是执行这项任务的另一种方式。在本文中，我们使用 max()提取最大值，并使用速记列表理解来迭代值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Maximum value from List keys
# Using max() + list comprehension

# initializing dictionary
test_dict = {"Gfg": 4, "is" : 5, "best" : 9, 
             "for" : 11, "geeks" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing list 
test_list = ["Gfg", "best", "geeks"]

# maximum is 11, but not present in list, 
# hence 9 is output.
res = max([test_dict[ele] for ele in test_list
           if ele in test_dict])

# printing result 
print("The required maximum : " + str(res)) 
```

**输出:**

> 最初的字典是:{'Gfg': 4，' is': 5，' best': 9，' for': 11，' geeks': 3}
> 要求的最大值:9