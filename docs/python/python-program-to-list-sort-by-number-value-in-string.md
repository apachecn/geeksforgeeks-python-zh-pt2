# Python 程序在字符串中列出按数字值排序

> 原文:[https://www . geesforgeks . org/python-程序到列表-按字符串中的数字值排序/](https://www.geeksforgeeks.org/python-program-to-list-sort-by-number-value-in-string/)

给定一个字符串列表，任务是编写一个 Python 程序，按照字符串中的数字对列表进行排序。如果没有号码，他们将被带到名单的前面。

> **输入**:test _ list =【“gfg 为 4”、“全 no . 1”、“极客遍 7 海”、“和 100 大行星”】
> **输出**:【“全 no . 1”、“gfg 为 4”、“极客遍 7 海”、“和 100 大行星”】
> **解释** : 1 < 4 < 7 < 100，字符串中的数字决定顺序。
> 
> **输入**:test _ list =【“gfg 为 4”、“极客遍 7 海”、“百大行星”】
> **输出**:【“gfg 为 4”、“极客遍 7 海”、“百大行星”】
> **解释** : 4 < 7 < 100，字符串中的数字决定顺序。

**方法 1 :** *使用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/)*[*拆分()*](https://www.geeksforgeeks.org/python-string-split/) *和*[*is digit()*](https://www.geeksforgeeks.org/python-string-isdigit-application/)*

*在本文中，我们使用 sort()执行就地排序任务，使用 split()执行从字符串中获取数字的任务，并使用 isdigit()完成最终检测。*

***示例:***

## *蟒蛇 3*

```
*import sys

def num_sort(strn):

    # getting number using isdigit() and split()
    computed_num = [ele for ele in strn.split() if ele.isdigit()]

    # assigning lowest weightage to strings 
    # with no numbers
    if len(computed_num) > 0:
        return int(computed_num[0])
    return -1

# initializing Matrix
test_list = ["gfg is", "all no 7", "geeks over seas", "and planets 5"]

# printing original list
print("The original list is : " + str(test_list))

# performing sort
test_list.sort(key=num_sort)

# printing result
print("Sorted Strings : " + str(test_list))*
```

***输出:***

> *最初的名单是:['gfg is '，' all no . 7 '，' geeks over seas '，'和行星 5']*
> 
> *排序字符串:['gfg 是'，'海洋上的极客'，'和行星 5 '，'都没有 7']*

***方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*[*拆分()*](https://www.geeksforgeeks.org/python-string-split/) *和*[*is digit()*](https://www.geeksforgeeks.org/python-string-isdigit-application/)***

**在这种情况下，lambda 函数用于注入使用 sorted()执行的排序功能。Rest 每个过程都类似于上面解释的方法。**

****示例:****

## **蟒蛇 3**

```
**# initializing Matrix
test_list = ["all no 100", "gfg is", "geeks over seas 62", "and planets 3"]

# printing original list
print("The original list is : " + str(test_list))

# performing sorting
# lambda function injecting functionality
res = sorted(test_list, key=lambda strn: -1 
             if len([ele for ele in strn.split() 
                     if ele.isdigit()]) == 0 
             else int([ele for ele in strn.split() 
                       if ele.isdigit()][0]))

# printing result
print("Sorted Strings : " + str(res))**
```

****输出:****

> **最初的名单是:['所有第 100 名'，' gfg is '，'极客飞越海洋 62 '，'和行星 3']**
> 
> **排序字符串:['gfg 是'，'和行星 3 '，'海洋上的极客 62 '，'都没有 100']**