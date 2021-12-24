# Python |漂亮用字典值

打印字典

> 原文:[https://www . geesforgeks . org/python-俏丽-print-a-dictionary-with-dictionary-value/](https://www.geeksforgeeks.org/python-pretty-print-a-dictionary-with-dictionary-value/)

本文只是提供了一种快速打印字典的方法，该字典以字典作为值。随着 NoSQL 数据库的出现，这一要求现在已经有很多次了。让我们编写一种方法来执行这个特定的任务。

**方法:使用循环**
我们只是使用蛮力的循环方式循环遍历每个字典元素及其对应的值。

```py
# Python3 code to demonstrate working of
# Pretty Print a dictionary with dictionary value
# Using loops

# initializing dictionary
test_dict = {'gfg' : {'rate' : 5, 'remark' : 'good'}, 'cs' : {'rate' : 3}}

# printing original dictionary
print("The original dictionary is : " +  str(test_dict))

# using loops to Pretty Print
print("The Pretty Print dictionary is : ")
for sub in test_dict:
    print (sub)
    for sub_nest in test_dict[sub]:
        print (sub_nest, ':', test_dict[sub][sub_nest])
```

**Output :**

```py
The original dictionary is : {'gfg': {'remark': 'good', 'rate': 5}, 'cs': {'rate': 3}}
The Pretty Print dictionary is : 
gfg
remark : good
rate : 5
cs
rate : 3

```