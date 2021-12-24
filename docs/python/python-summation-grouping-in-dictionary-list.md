# Python–字典列表中的求和分组

> 原文:[https://www . geesforgeks . org/python-summary-group-in-dictionary-list/](https://www.geeksforgeeks.org/python-summation-grouping-in-dictionary-list/)

有时，在使用 Python Dictionaries 时，我们会遇到一个问题，即需要根据特定的键对字典进行分组，并在对相似键的值进行分组时对某些键进行求和。这是一个特殊的问题，但可以应用于诸如 web 开发等领域。让我们讨论一下执行这项任务的特定方式。

> **输入:** test_list = [{ '极客':10，'最佳':8，' Gfg': 6}，{ '极客':12，'最佳':11，' Gfg': 4}]
> **输出:** {4: { '极客':12，'最佳':11}，6: { '极客':10，'最佳':8}}
> 
> **输入:** test_list = [{'CS': 14、' best': 9、'极客':7、' Gfg': 14}]
> **输出:** {14: {'best': 9、'极客':7}}

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们手动循环字典中的每个关键字，并根据关键字执行所需的分组，并构建所需的分组和汇总字典。

```
# Python3 code to demonstrate working of 
# Summation Grouping in Dictionary List
# Using loop

# initializing list
test_list = [{'Gfg' :  1, 'id' : 2, 'best' : 8, 'geeks' : 10}, 
             {'Gfg' :  4, 'id' : 4, 'best':  10, 'geeks' : 12}, 
             {'Gfg' :  4, 'id' : 8, 'best':  11, 'geeks' : 15}]

# printing original list
print("The original list is : " + str(test_list))

# initializing group key 
grp_key = 'Gfg'

# initializing sum keys 
sum_keys = ['best', 'geeks']

# Summation Grouping in Dictionary List
# Using loop
res = {}
for sub in test_list:
    ele = sub[grp_key]
    if ele not in res:
        res[ele] = {x: 0 for x in sum_keys}
    for y in sum_keys:
        res[ele][y] += int(sub[y])

# printing result 
print("The grouped list : " + str(res)) 
```

**Output :**

> 原始列表为:[{ '极客':10，' id': 2，' best': 8，' Gfg': 1}，{ '极客':12，' id': 4，' best': 10，' Gfg': 4}，{ '极客':15，' id': 8，' best': 11，' Gfg': 4}]
> 分组列表:{1: { '极客':10，' best': 8}，4: { '极客':27，' best': 21}}