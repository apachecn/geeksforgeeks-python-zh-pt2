# Python–按值对嵌套键进行排序

> 原文:[https://www . geesforgeks . org/python-sort-nested-key-by-value/](https://www.geeksforgeeks.org/python-sort-nested-keys-by-value/)

有时，在处理数据记录时，我们可能会遇到一个问题，即我们需要根据出现值对字典的嵌套键进行排序。这可以应用于排列分数、价格等。让我们讨论一下执行这项任务的方法。

**方法#1:使用`sorted()` + lambda +生成器表达式**
以上方法的组合可用于执行此任务。在本文中，我们使用 sorted()执行排序任务，lambda 和 generator 表达式用于绑定和提取字典的值。

```py
# Python3 code to demonstrate working of 
# Sort Nested keys by Value
# Using sorted() + generator expression + lamda

# initializing dictionary
test_dict = {'Nikhil' : {'English' : 5, 'Maths' :  2, 'Science' : 14},
             'Akash' : {'English' : 15, 'Maths' :  7, 'Science' : 2},
             'Akshat' : {'English' : 5, 'Maths' :  50, 'Science' : 20}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Sort Nested keys by Value
# Using sorted() + generator expression + lamda
res = {key : dict(sorted(val.items(), key = lambda ele: ele[1]))
       for key, val in test_dict.items()}

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output :**

> 原版词典:{'Nikhil': {'English': 5，'数学':2，' Science': 14}，' Akash': {'English': 15，'数学':7，' Science': 2}，' Akshat': {'English': 5，'数学':50，' Science': 20}}
> 排序后的词典:{'Nikhil': { '数学':2，'英语':5，' Science': 14 '，' Akash': {'Science': 2，'数学':7，'英语':15}，' Akshat ':