# 从字典中删除重复的 Python 程序

> 原文:[https://www . geesforgeks . org/python-从字典中删除程序-表里不一/](https://www.geeksforgeeks.org/python-program-to-remove-duplicity-from-a-dictionary/)

给定一个以值为列表的字典，任务是编写一个 Python 程序，该程序可以删除字典中的内容，而不管它们是多次出现的键还是值。

> **输入:** {'gfg' : ['gfg '，' is '，' best']，' best' : ['gfg']，' apple' : ['good']}
> 
> **输出:** {'gfg': ['gfg '，' is '，' best']，' apple': ['good']}
> 
> **说明**:最佳键省略，因为它已经是第一个键的值。
> 
> **输入:** {'gfg' : ['gfg '，' is '，' best '，' apple']，' best' : ['gfg']，' apple' : ['good']}
> 
> **输出:** {'gfg': ['gfg '，' is '，' best '，' apple']}
> 
> **说明:** best 和 apple 键省略，因为它已经是第一个键的值。

**进场:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和物品()*

在这种情况下，我们对每个键进行迭代，并使用 items()提取其值，并记住它们，键和值被省略以在它们已经出现的情况下被添加/创建。

**程序:**

## 蟒蛇 3

```
# initializing dictionary
test_dict = {'gfg': ['gfg', 'is', 'best'],
             'best': ['gfg'],
             'apple': ['good']}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = dict()
for key, val in test_dict.items():

    flag = True
    for key1, val1 in res.items():

        # filtering value from memoised values
        if key in val1:
            flag = False
    if flag:
        res[key] = val

# printing result
print("The filtered dictionary : " + str(res))
```

**输出:**

> 原词典为:{'gfg': ['gfg '，' is '，' best']，' best': ['gfg']，' apple': ['good']}
> 
> 筛选的字典:{'gfg': ['gfg '，' is '，' best']，' apple': ['good']}