# Python–字典中唯一的值键，以列表作为值

> 原文:[https://www . geesforgeks . org/python-唯一值-字典中的键-列表-作为值/](https://www.geeksforgeeks.org/python-unique-value-keys-in-a-dictionary-with-lists-as-values/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即我们需要提取值为**唯一的键(其他列表中应该至少有一个项目不存在)**，即不出现在任何其他键的值列表中。这可以在数据预处理中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `count()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用计数和提取来执行计数事件的任务，并且使用使用条件语句的循环来完成测试。

```
# Python3 code to demonstrate working of 
# Unique Keys Values
# Using loop + count()

# initializing dictionary
test_dict = {'Gfg' : [6, 5], 'is' : [6, 10, 5], 'best' : [12, 6, 5]} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Unique Keys Values
# Using loop + count()
temp = [sub for ele in test_dict.values() for sub in ele]
res = []
for key, vals in test_dict.items():
    for val in vals:
        if temp.count(val) == 1:
            res.append(key)
            break

# printing result 
print("The unique values keys are : " + str(res)) 
```

**Output :**

```
The original dictionary is : {'Gfg': [6, 5], 'best': [12, 6, 5], 'is': [6, 10, 5]}
The unique values keys are : ['best', 'is']

```