# Python–列表上的值嵌套分组

> 原文:[https://www . geesforgeks . org/python-value-nested-group-on-list/](https://www.geeksforgeeks.org/python-value-nested-grouping-on-list/)

有时，在处理数据时，我们会遇到一个问题，即我们有字典列表形式的平面数据，我们需要根据 ids 从这些空白字典中执行分类。这可以应用于涉及数据的领域，如网络开发和数据科学。让我们讨论一下执行这项任务的具体方法。

**方法:使用`defaultdict() + setdefault()` +循环**
上述功能的组合可用于执行该任务。这是一种残忍的方式。在本文中，我们使用字典值初始化 defaultdict()，以形成嵌套记录，并使用 setdefault()和条件填充数据。

```
# Python3 code to demonstrate working of 
# Value nested grouping on List
# Using loop + setdefault() + defaultdict()
from collections import defaultdict

# initializing list
test_list = [{ 'value' : 'Fruit'},
             { 'tag' : 'Fruit', 'value' : 'mango'},
             { 'value' : 'Car'},
             { 'tag' : 'Car', 'value' : 'maruti'},
             { 'tag' : 'Fruit', 'value' : 'orange'},
             { 'tag' : 'Car', 'value' : 'city'}]

# printing original list
print("The original list is : " + str(test_list))

# Value nested grouping on List
# Using loop + setdefault() + defaultdict()
temp = defaultdict(dict)
res = {}
for sub in test_list:
    type = sub['value']
    if 'tag' in sub:
        tag = sub['tag']
        temp[tag].setdefault(type, temp[type])
    else:
        res[type] = temp[type]

# printing result 
print("The dictionary after grouping : " + str(res)) 
```

**Output :**

> 原列表为:[{'value ':'水果' }，{'tag ':'水果'，' value': 'mango'}，{'value': 'Car'}，{'tag': 'Car '，' value': 'maruti'}，{'tag ':'水果'，' value': 'city'}]
> 分组后的字典:{ '水果':{ ' mango ':}，' orange'}，' Car ':{ ' city ' }，' maruti': {}}