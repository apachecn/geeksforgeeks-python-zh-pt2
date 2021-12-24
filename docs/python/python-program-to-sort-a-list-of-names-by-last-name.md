# Python 程序按姓氏对名字列表进行排序

> 原文:[https://www . geesforgeks . org/python-program-to-sort-a-list-name-by-last-name/](https://www.geeksforgeeks.org/python-program-to-sort-a-list-of-names-by-last-name/)

给定一个名字列表，任务是编写一个 Python 程序，按照姓氏对名字列表进行排序。

**示例:**

> **输入:** ['疾速追杀'，'杰森·沃赫斯']
> 
> **输出:** ['杰森·沃赫斯'，'疾速追杀']
> 
> **说明:**杰森·沃赫斯伏羲的 V 小于疾速追杀威克的 W。
> 
> **输入:** ['弗莱迪·克鲁格'，'凯泽·索泽'，'莫欣德·辛格·潘德尔']
> 
> **输出:** ['弗莱迪·克鲁格'，'莫欣德·辛格·潘德尔'，'凯撒·索泽']
> 
> **说明:** K < P < S

**方法#1:** 在转换后的 [2D 列表](https://www.geeksforgeeks.org/python-using-2d-arrays-lists-the-right-way/)上使用 [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/) 方法。

将姓名列表转换为 2D 姓名列表，其中第一个索引指的是名字，最后一个索引指的是姓氏。应用*排序()*方法，将*键*作为 2D 列表中每个元素的最后一个索引。

## 蟒蛇 3

```
# explicit function sort names
# by their surnames
def sortSur(nameList):
    l2 = []

    # create 2d list of names
    for ele in nameList:
        l2.append(ele.split())
    nameList = []

    # sort by last name
    for ele in sorted(l2, key=lambda x: x[-1]):
        nameList.append(' '.join(ele))

    # return sorted list
    return nameList

# Driver Code

# assign list of names
nameList = ['John Wick', 'Jason Voorhees',
            'Freddy Krueger', 'Keyser Soze',
            'Mohinder Singh Pandher']

# display original list
print('\nList of Names:\n', nameList)
print('\nAfter sorting:\n', sortSur(nameList))
```

**输出:**

> 名单:
> ['疾速追杀'，'杰森·沃赫斯'，'弗莱迪·克鲁格'，'凯撒·索泽'，'莫欣德·辛格·潘德尔']
> 
> 排序后:
> ['弗莱迪·克鲁格'，'莫欣德·辛格·潘德尔'，'凯撒·索泽'，'杰森·沃赫斯'，'疾速追杀']

**方法#2:** 使用 [*排序()*](https://www.geeksforgeeks.org/sort-in-python/) 方法+[*λ*](https://www.geeksforgeeks.org/python-lambda/)

在给定的名称列表中使用 *sort()* 方法，用*键*作为*λx:x . split()[-1])，*代表列表中每个元素的最后一个字符串。

## 蟒蛇 3

```
# explicit function sort names
# by their surnames
def sortSur(nameList):

    # sort list by last name
    nameList.sort(key=lambda x: x.split()[-1])

    # return sorted list
    return nameList

# Driver Code

# assign list of names
nameList = ['John Wick', 'Jason Voorhees',
            'Freddy Krueger', 'Keyser Soze',
            'Mohinder Singh Pandher']

# display original list
print('\nList of Names:\n', nameList)
print('\nAfter sorting:\n', sortSur(nameList))
```

**输出:**

> 名单:
> ['疾速追杀'，'杰森·沃赫斯'，'弗莱迪·克鲁格'，'凯撒·索泽'，'莫欣德·辛格·潘德尔']
> 
> 排序后:
> ['弗莱迪·克鲁格'，'莫欣德·辛格·潘德尔'，'凯撒·索泽'，'杰森·沃赫斯'，'疾速追杀']