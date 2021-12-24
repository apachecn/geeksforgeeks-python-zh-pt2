# Python 程序连接等层次字符串

> 原文:[https://www . geesforgeks . org/python-程序-加入-等价-层次-字符串/](https://www.geeksforgeeks.org/python-program-to-join-equi-hierarchy-strings/)

给定一个具有多个层次的字符串列表，任务是编写一个 python 程序来连接那些具有相同层次的字符串。

已知在维度更改之前，同一维度中的元素位于同一层次结构中。

> **输入:**test _ list =[“gfg”、“best”、[“for”、“all”]、“all”、[“CS”、“极客”]]
> 
> **输出:** ['gfg best '，[' for all ']，' all '，[' CS 极客']]
> 
> **解释:**处于类似连接层次的字符串。
> 
> **输入:**test _ list =[“gfg”、“best”、[“for”、“all”]、[“CS”、“极客”]]
> 
> **输出:** ['gfg 最佳'，['适合所有人']，[' CS 极客']]
> 
> **解释:**处于类似连接层次的字符串。

**方法 1 :** 使用[类型()](https://www.geeksforgeeks.org/python-type-function/)、[循环](https://www.geeksforgeeks.org/loops-in-python/)、[递归](https://www.geeksforgeeks.org/recursion-in-python/)和[连接()](https://www.geeksforgeeks.org/join-function-python/)

在这种情况下，使用 type()检查列表元素是否为字符串，如果找到，则使用该层次结构的 join 执行联接任务。如果发现元素是列表，则为下一层次的类似逻辑重复内部列表。

**示例:**

## 蟒蛇 3

```
def hierjoin(test_list):
    res = []
    temp = []
    val = None
    for sub in test_list:

        # if string then appended
        if type(sub) == str:
            temp.append(sub)

        # if list, the string is joined for hierarchy
        # recurred for inner list
        else:
            res.append(''.join(temp))
            temp = []
            val = hierjoin(sub)
            res.append(val)
    if temp != []:
        res.append(''.join(temp))
    return res

# initializing list
test_list = ["gfg ", " best ", [" for ", " all "],
             " all ", [" CS ", " geeks "]]

# printing original list
print("The original list is : " + str(test_list))

# calling recursion
res = hierjoin(test_list)

# printing result
print("The joined strings : " + str(res))
```

**输出:**

> 最初的名单是:['gfg '，' best '，[' for '，' all ']，' all '，[' CS '，' geeks ']]
> 
> 连接的字符串:['gfg best '，[' for all ']，' all '，[' CS geeks ']]

**方法 2 :** 使用[连接()](https://www.geeksforgeeks.org/join-function-python/)、[映射()](https://www.geeksforgeeks.org/python-map-function/)、[递归](https://www.geeksforgeeks.org/recursion-in-python/)和 [groupby()](https://www.geeksforgeeks.org/python-pandas-dataframe-groupby/)

在这个等价层次结构中，组是使用 groupby()形成的。然后使用 map()调用列表字符串内部层次的递归函数。

**示例:**

## 蟒蛇 3

```
from itertools import groupby

def hierjoin(test_list):

    # groups are formed for similar hierarchy using groupby
    return [idx for x, y in groupby(test_list, key=str.__instancecheck__)
            for idx in ([''.join(y)] if x else map(hierjoin, y))]

# initializing list
test_list = ["gfg ", " best ", [" for ", " all "],
             " all ", [" CS ", " geeks "]]

# printing original list
print("The original list is : " + str(test_list))

# calling recursion
res = hierjoin(test_list)

# printing result
print("The joined strings : " + str(res))
```

**输出:**

> 最初的名单是:['gfg '，' best '，[' for '，' all ']，' all '，[' CS '，' geeks ']]
> 
> 连接的字符串:['gfg best '，[' for all ']，' all '，[' CS geeks ']]