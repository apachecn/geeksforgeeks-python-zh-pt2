# Python–从字典嵌套中移除 K 值项

> 原文:[https://www . geesforgeks . org/python-remove-k-value-items-from-dictionary-nesting/](https://www.geeksforgeeks.org/python-remove-k-value-items-from-dictionary-nesting/)

给定具有多个嵌套的字典，移除所有值为 k 的键。

> **输入**:[{“Gfg”:{“a”:5，“b”:8，“c”:9 } }，{“is”:{“j”:8，“K”:10 } }，{“Best”:{“I”:16 } }]，K = 8
> **输出**:[{‘a’:5 }，{‘c’:9 }，{‘K’:10 }，{‘I’:16 }]
> **解释**:值为 8 的所有键，(()
> 
> **输入**:[{“Gfg”:{“a”:5，“b”:8，“c”:9 } }，{“is”:{“j”:8，“K”:10 } }，{“Best”:{“I”:16 } }]，K = 5
> **输出**:[{“c”:9 }，{“K”:10 }，{“I”:16 }，{“j”:8 }，{“b”:8 }]
> **解释**:”

**方法一:使用循环+词典理解**

上述功能的组合可以用来解决这个问题。在这里，我们使用循环迭代所有的嵌套键。并删除值。这种方法适用于字典的单层嵌套。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove K value items from dictionary nestings
# Using dictionary comprehension + loop

# initializing list
test_list = [{"Gfg" : {"a" : 5, "b" : 8, "c" : 9}},
             {"is" : {"f" : 8, "j" : 8, "k" : 10}},
             {"Best" : {"i" : 16}}]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 8

res = list()

for sub in test_list:
    for key, val in sub.items():

        # iterating for 1st nesting only
        for key1, val1 in val.items():
            if val1 != K:
                res.append({key1 : val1})

# printing result 
print("The dictionary after value removal : " + str(res)) 
```

**Output**

> 原始列表为:[{'Gfg': {'a': 5，' b': 8，' c': 9}}，{'is': {'f': 8，' j': 8，' k': 10}}，{'Best': {'i': 16}}]
> 值移除后的字典:[{'a': 5}，{'c': 9}，{'k': 10}，{'i': 16}]

**方法 2:使用递归+循环(用于多重嵌套)**

这是执行这项任务的另一种方式。在本文中，我们解决了一个更一般的问题，即既要满足内部字典元素，又要使用递归。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove K value items from dictionary nestings
# Using recursion + loop (For multiple nesting)

res = []

# helper function to solve problem
def hlper_fnc(test_dict):
    for key in test_dict:
        if type(test_dict[key]) == dict:
            hlper_fnc(test_dict[key])
        else:
            if test_dict[key] != K:
                res.append({key : test_dict[key]})

# initializing dictionary
test_dict = {"Gfg" : {"a" : 5, "b" : 8, "c" : 9},
             "is" : {"f" : 8, "l" : { "j" : 8, "k" : 10}},
             "Best" : {"i" : {"k" : { "o" : 8}}}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 8

# computing result
hlper_fnc(test_dict)

# printing result 
print("The dictionary after value removal : " + str(res)) 
```

**Output**

> 原始字典为:{'Gfg': {'a': 5，' b': 8，' c': 9}，' is': {'f': 8，' l': {'j': 8，' k': 10}}，' Best ':{ ' I ':{ ' k ':{ ' o ':8 } } }
> 值移除后的字典:[{'a': 5}，{'c': 9}，{'k': 10}]