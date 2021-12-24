# Python |字典中的优先键分配

> 原文:[https://www . geesforgeks . org/python-priority-key-assignment-in-dictionary/](https://www.geeksforgeeks.org/python-priority-key-assignment-in-dictionary/)

有时，在使用字典时，我们有一个应用程序，其中我们需要分配一个变量，该变量具有来自任何给定键的单个值，以优先级中最先出现的为准。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这个任务可以使用循环以蛮力的方式执行。在这种情况下，我们可以循环遍历字典键和优先级列表。如果我们找到了键，我们就中断并给变量赋值。

```py
# Python3 code to demonstrate working of
# Priority key assignment in dictionary
# Using loop

# Initialize dictionary
test_dict = {'gfg' : 6, 'is' : 4, 'for' : 2, 'CS' : 10}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Initialize priority keys
prio_list = ['best', 'gfg', 'CS']

# Using loop
# Priority key assignment in dictionary
res = None
for key in test_dict:
    if key in prio_list :
        res = test_dict[key]
        break

# printing result 
print("The variable value after assignment : " + str(res))
```

**Output :**

```py
The original dictionary : {'gfg': 6, 'is': 4, 'CS': 10, 'for': 2}
The variable value after assignment : 6

```