# Python 程序提取自定义值的字典项

> 原文:[https://www . geesforgeks . org/python-程序-提取-字典-项目-自定义-值/](https://www.geeksforgeeks.org/python-program-to-extract-dictionary-items-for-custom-values/)

给定一个字典，提取列表中匹配给定值的所有项目

**示例:**

> **输入**:test _ dict = {“Gfg”:3、“is”:5、“for”:8、“Geeks”:10、“Best”:16 }、sub_list = [5、4、10、20、16、8]
> **输出**:{“is”:5、“Geeks”:10、“Best”:16、“for”:8 }
> **解释**:所有匹配列表值的值随键一起提取。
> 
> **输入**:test _ dict = {“Gfg”:3、“is”:5、“for”:8、“极客”:10、“最佳”:16 }、sub_list = [5、4、10]
> **输出**:{“is”:5、“极客”:10}
> **解释**:所有匹配列表值的值都随键一起提取。

**方法 1:使用循环**

将**用于循环**是执行该任务的方法之一。在这种情况下，我们对所有键进行迭代，并检查该值是否出现在自定义列表中，如果是，则返回。

## 蟒蛇 3

```
# initializing dictionary
test_dict = {"Gfg": 3, "is": 5, "for": 8,
             "Geeks": 10, "Best": 16}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing list
sub_list = [5, 4, 10, 20, 16]

# Using loop to perform iteration
res = dict()

for key in test_dict:

    if test_dict[key] in sub_list:
        res[key] = test_dict[key]

# printing result
print("Extracted items : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': 3，' is': 5，' for': 8，' Geeks': 10，' Best': 16}
> 提取项:{'is': 5，' Geeks': 10，' Best': 16}

**方法二:利用词典理解**

这是一个单行的帮助下，这项任务可以执行。在这种情况下，我们使用[字典理解](https://www.geeksforgeeks.org/python-dictionary-comprehension/)在单行方法中对所有键进行迭代。

## 蟒蛇 3

```
# initializing dictionary
test_dict = {"Gfg": 3, "is": 5, "for": 8,
             "Geeks": 10, "Best": 16}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing list
sub_list = [5, 4, 10, 20, 16]

# dictionary comprehension to compile logic in one dictionary
# in operator used to check value existance
res = {key: val for key, val in test_dict.items() if val in sub_list}

# printing result
print("Extracted items : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': 3，' is': 5，' for': 8，' Geeks': 10，' Best': 16}
> 提取项:{'is': 5，' Geeks': 10，' Best': 16}