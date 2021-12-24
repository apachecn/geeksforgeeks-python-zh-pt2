# 使用 Python 中的第二个列表对第一个列表的值进行排序

> 原文:[https://www . geesforgeks . org/python-sort-values-first-list-use-second-list/](https://www.geeksforgeeks.org/python-sort-values-first-list-using-second-list/)

给定两个列表，使用第二个列表对一个列表的值进行排序。

**示例:**

```
Input : list1 = ["a", "b", "c", "d", "e", "f", "g", "h", "i"]
        list2 = [ 0,   1,   1,    0,   1,   2,   2,   0,   1]

Output :['a', 'd', 'h', 'b', 'c', 'e', 'i', 'f', 'g']

Input : list1 = ["g", "e", "e", "k", "s", "f", "o", "r", "g", "e", "e", "k", "s"]
        list2 = [ 0,   1,   1,    0,   1,   2,   2,   0,   1]

Output : ['g', 'k', 'r', 'e', 'e', 'g', 's', 'f', 'o']

```

**进场:**

1.  把这两份名单压缩。
2.  使用 sorted()基于 zip 创建一个新的排序列表。
3.  使用列表理解从排序的压缩列表中提取每对的第一个元素。

**概念:**
zip()的目的是映射多个容器的相似索引，以便它们可以作为单个实体使用。
以下是上述办法的实施:

## 计算机编程语言

```
# Python program to sort
# one list using
# the other list

def sort_list(list1, list2):

    zipped_pairs = zip(list2, list1)

    z = [x for _, x in sorted(zipped_pairs)]

    return z

# driver code
x = ["a", "b", "c", "d", "e", "f", "g", "h", "i"]
y = [ 0,   1,   1,    0,   1,   2,   2,   0,   1]

print(sort_list(x, y))

x = ["g", "e", "e", "k", "s", "f", "o", "r", "g", "e", "e", "k", "s"]
y = [ 0,   1,   1,    0,   1,   2,   2,   0,   1]

print(sort_list(x, y))
```

**输出:**

```
['a', 'd', 'h', 'b', 'c', 'e', 'i', 'f', 'g']
['g', 'k', 'r', 'e', 'e', 'g', 's', 'f', 'o']

```

在上面的代码中，我们有两个列表，第一个列表根据第二个列表的值进行排序。

```
y = [ 0,   1,   1,    0,   1,   2,   2,   0,   1]

```

这里首先检查最低值。就像这个列表，0 是最低的，所以从第一个索引开始，0 是最低的，它在索引 0 处。所以索引 0 的值存储在第一个列表的索引 0 处。类似地，在索引 3 处再次发现 0，因此第一个列表中索引 3 的值是索引 1。同样的情况会持续到列表没有完成。

**方法二:利用字典、列表理解、lambda 函数**

## 蟒蛇 3

```
def sorting_of_element(list1,list2):

    # initializing blank dictionary
    f_1 = {}

    # initializing blank list
    final_list = []

    # Addition of two list in one dictionary
    f_1 = {list1[i]: list2[i] for i in range(len(list2))}

    # sorting of dictionary based on value
    f_lst = {k: v for k, v in sorted(f_1.items(), key=lambda item: item[1])}

    # Element addition in the list
    for i in f_lst.keys():
        final_list.append(i)
    return final_list

list1 = ["a", "b", "c", "d", "e", "f", "g", "h", "i"]
list2 = [ 0,   1,   1,    0,   1,   2,   2,   0,   1]

sorting_of_element(list1,list2)
```

**输出:**

```
['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i']

```