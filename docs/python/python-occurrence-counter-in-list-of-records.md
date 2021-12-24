# Python–记录列表中的出现计数器

> 原文:[https://www . geesforgeks . org/python-出现-记录列表中的计数器/](https://www.geeksforgeeks.org/python-occurrence-counter-in-list-of-records/)

有时，在处理记录时，我们会遇到一个问题，即我们需要计算游戏中不同角色/玩家对应的输入数字的出现次数，并将其编译到字典中。这可以在游戏和网络开发中得到应用。让我们来讨论一下如何做到这一点。

**方法:使用 loop + `Counter()`**
以上功能的组合可以用来执行这个任务。在本文中，我们使用 Counter()对元素进行迭代并计算频率，唯一字符由字典的键管理。

```py
# Python3 code to demonstrate 
# Occurrence counter in List of Records
# using Counter() + loop
from collections import Counter

# Initializing list
test_list = [('Gfg', 1), ('Gfg', 2), ('Gfg', 3), ('Gfg', 1), ('Gfg', 2), ('is', 1), ('is', 2)]

# printing original list
print("The original list is : " + str(test_list))

# Occurrence counter in List of Records
# using Counter() + loop
res = {}
for key, val in test_list:
    res[key] = [val] if key not in res else res[key] + [val]

res = {key: dict(Counter(val)) for key, val in res.items()}

# printing result 
print ("Mapped resultant dictionary : " + str(res))
```

**Output :**

> 原始列表为:[('Gfg '，1)、(' Gfg '，2)、(' Gfg '，3)、(' Gfg '，1)、(' Gfg '，2)、(' is '，1)、(' is '，2)]
> 映射结果词典:{'is': {1: 1，2: 1}、' Gfg': {1: 2，2: 2，3: 1}}