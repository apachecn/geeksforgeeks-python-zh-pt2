# Python |合并两个不同列表的对应子列表

> 原文:[https://www . geesforgeks . org/python-merge-对应-子列表-来自-两个-不同-列表/](https://www.geeksforgeeks.org/python-merge-corresponding-sublists-from-two-different-lists/)

给定两个包含子列表的列表，编写一个 Python 程序，根据相同的索引合并这两个子列表。

**示例:**

```py
Input : l1 = [['+', '-', '+'], ['-', '+'], ['+', '-', '+']]
        l2 = [['2a3', 'b2', '3c'], ['a3', 'b2'], ['a3', '2b2', '5c']]
Output : [['+2a3', '-b2', '+3c'], ['-a3', '+b2'], ['+a3', '-2b2', '+5c']]

Input : l1 = [['1', '2'], ['1', '2', '3']]
        l2 = [['anne', 'bob'], ['cara', 'drake', 'ezra']]
Output : [['1anne', '2bob'], ['1cara', '2drake', '3ezra']]

```

**方法#1 :** 用`zip()`
进行列表理解我们可以用`zip()`函数进行嵌套列表理解。`zip()`函数接受 iterable，生成基于传递的 iterable 聚合元素的迭代器，并返回元组的迭代器。现在使用两个变量 *i* 和 *j* 遍历压缩的元组，它使用“+”运算符连接两个变量。

```py
# Python3 code to Concatenate 
# corresponding sublists from two 
# different lists

def concatList(l1, l2):
    return [[i + j for i, j in zip(x, y)]
                 for x, y in zip(l1, l2)]

# Driver Code
l1 = [['1', '2'], ['1', '2', '3']]
l2 = [['anne', 'bob'], ['cara', 'drake', 'ezra']]
print(concatList(l1, l2))
```

**Output:**

```py
[['1anne', '2bob'], ['1cara', '2drake', '3ezra']]

```

**用`map()`
逼近#2 :** 列表理解我们可以用函数*映射()*和运算符*串联*来代替嵌套列表理解。我们使用变量 *i* 和 *j* 遍历压缩的*列表 1* 和*列表 2* 。然后我们在 *i* 和 *j* 上应用 concat 运算符来连接它们。

```py
# Python3 code to Concatenate 
# corresponding sublists from two 
# different lists
from operator import concat

def concatList(l1, l2):
    return [list(map(concat, i, j)) for i, j in zip(l1, l2)]

# Driver Code
l1 = [['1', '2'], ['1', '2', '3']]
l2 = [['anne', 'bob'], ['cara', 'drake', 'ezra']]
print(concatList(l1, l2))
```

**Output:**

```py
[['1anne', '2bob'], ['1cara', '2drake', '3ezra']]

```