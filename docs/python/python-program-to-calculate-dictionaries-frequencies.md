# Python 程序计算字典频率

> 原文:[https://www . geesforgeks . org/python-程序到计算-字典-频率/](https://www.geeksforgeeks.org/python-program-to-calculate-dictionaries-frequencies/)

给定一个字典列表，这里的任务是编写一个 python 程序来提取每个字典的字典频率。

> **输入:** test_list = [{'gfg' : 1，' is' : 4，' best' : 9}，
> 
> {'gfg' : 6，' is' : 3，' best' : 8}，
> 
> {“gfg”:1，“is”:4，“best”:9 }，
> 
> {“gfg”:1，“is”:1，“best”:9 }，
> 
> {“gfg”:6，“is”:3，“best”:8 }]
> 
> **输出:** [({'gfg': 1，' is': 4，' best': 9}，2)、({'gfg': 6，' is': 3，' best': 8}，2)、({'gfg': 1，' is': 1，' best': 9}，1)]
> 
> **说明:**字典，其频率作为结果附加在列表中。
> 
> **输入:** test_list = [{'gfg' : 1，' is' : 4，' best' : 9}，
> 
> {'gfg' : 6，' is' : 3，' best' : 8}，
> 
> {“gfg”:1，“is”:4，“best”:9 }，
> 
> {“gfg”:1，“is”:1，“best”:9 }]
> 
> **输出:** [({'gfg': 1，' is': 4，' best': 9}，2)、({'gfg': 6，' is': 3，' best': 8}，1)、({'gfg': 1，' is': 1，' best': 9}，1)]
> 
> **说明:**字典，其频率作为结果附加在列表中。

**方法 1 :** *使用* [*索引()*](https://www.geeksforgeeks.org/python-list-index/#:~:text=index()%20is%20an%20inbuilt,index%20where%20the%20element%20appears.&text=Parameters%20%3A,from%20where%20the%20search%20begins.) *和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，每个字典都被迭代，并使用 index()来获得字典的索引，该索引随着其频率的增加而映射，并且在字典重复的情况下递增计数器。

**示例:**

## 蟒蛇 3

```py
# initializing list
test_list = [{'gfg': 1, 'is': 4, 'best': 9},
             {'gfg': 6, 'is': 3, 'best': 8},
             {'gfg': 1, 'is': 4, 'best': 9},
             {'gfg': 1, 'is': 1, 'best': 9},
             {'gfg': 6, 'is': 3, 'best': 8}]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:

    flag = 0
    for ele in res:

        # checking for presence and incrementing frequency
        if sub == ele[0]:
            res[res.index(ele)] = (sub, ele[1] + 1)
            flag = 1

    if not flag:
        res.append((sub, 1))

# printing result
print("Dictionaries frequencies : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 1，' is': 4，' best': 9}，{'gfg': 6，' is': 3，' best': 8}，{'gfg': 1，' is': 4，' best': 9}，{'gfg': 1，' is': 1，' best': 9}，{'gfg': 6，' is': 3，' best': 8}]
> 
> 字典频率:[({'best': 9，' gfg': 1，' is': 4}，2)，({'best': 8，' gfg': 6，' is': 3}，2)，({'best': 9，' gfg': 1，' is': 1}，1)]

**方法二:** *使用* [*计数器()*](https://www.geeksforgeeks.org/python-counter-objects-elements/) *和* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)

在这种情况下，字典元素被转换成元组对，然后使用计数器来获取每个元组对的频率。在最后一步，每本词典都被重新转换成原来的形式。

**示例:**

## 蟒蛇 3

```py
from collections import Counter

# initializing list
test_list = [{'gfg': 1, 'is': 4, 'best': 9},
             {'gfg': 6, 'is': 3, 'best': 8},
             {'gfg': 1, 'is': 4, 'best': 9},
             {'gfg': 1, 'is': 1, 'best': 9},
             {'gfg': 6, 'is': 3, 'best': 8}]

# printing original list
print("The original list is : " + str(test_list))

# getting frequencies
temp = Counter(tuple(sorted(sub.items())) for sub in test_list)

# converting back to Dictionaries
res = [(dict([tuple(ele) for ele in sub]), temp[sub]) for sub in temp]

# printing result
print("Dictionaries frequencies : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 1，' is': 4，' best': 9}，{'gfg': 6，' is': 3，' best': 8}，{'gfg': 1，' is': 4，' best': 9}，{'gfg': 1，' is': 1，' best': 9}，{'gfg': 6，' is': 3，' best': 8}]
> 
> 字典频率:[({'best': 9，' gfg': 1，' is': 4}，2)，({'best': 8，' gfg': 6，' is': 3}，2)，({'best': 9，' gfg': 1，' is': 1}，1)]