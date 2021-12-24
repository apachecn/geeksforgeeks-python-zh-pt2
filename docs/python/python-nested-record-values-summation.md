# Python–嵌套记录值求和

> 原文:[https://www . geesforgeks . org/python-nested-record-values-summary/](https://www.geeksforgeeks.org/python-nested-record-values-summation/)

有时，在处理记录时，我们可能会遇到这样的问题:我们需要对一个键的嵌套键执行求和，并将求和记录为键的值。这在数据科学和网络开发等领域可能有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是我们执行这个任务的蛮力方式。在这种情况下，我们遍历嵌套字典，对值求和并分配给相应的键。

```
# Python3 code to demonstrate working of 
# Nested record values summation
# Using loop

# initializing dictionary
test_dict = {'gfg' : {'a' : 4, 'b' : 5, 'c' : 6},
             'is' : {'a': 2, 'b' : 9, 'c' : 10},
             'best' : {'a' : 10, 'b' : 2, 'c' : 12}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Nested record values summation
# Using loop
res = dict()
for sub in test_dict:
    sum = 0
    for keys in test_dict[sub]:
        sum = sum + test_dict[sub][keys]
    res[sub] = sum

# printing result 
print("The dictionary after keys summation is : " + str(res)) 
```

**Output :**

```
The original dictionary is : {'best': {'a': 10, 'c': 12, 'b': 2}, 'is': {'a': 2, 'c': 10, 'b': 9}, 'gfg': {'a': 4, 'c': 6, 'b': 5}}
The dictionary after keys summation is : {'best': 24, 'is': 21, 'gfg': 15}

```