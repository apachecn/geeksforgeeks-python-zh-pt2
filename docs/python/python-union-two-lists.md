# Python |两个或多个列表的并集

> 原文:[https://www.geeksforgeeks.org/python-union-two-lists/](https://www.geeksforgeeks.org/python-union-two-lists/)

列表的并集意味着，我们必须从列表 A 和列表 B 中取出所有元素(可以有两个以上的列表)，并将它们放在一个新的列表中。我们可以按照不同的顺序组合这些列表。例如，我们可以保持重复和顺序，或者删除最终列表中重复的元素，等等。
示例:

```py
Maintained repetition only
Input : 
lst1 = [23, 15, 2, 14, 14, 16, 20 ,52]
lst2 = [2, 48, 15, 12, 26, 32, 47, 54]
Output :
[23, 15, 2, 14, 14, 16, 20, 52, 2, 48, 
15, 12, 26, 32, 47, 54]

Maintained repetition and order
Input : 
lst1 = [23, 15, 2, 14, 14, 16, 20 ,52]
lst2 = [2, 48, 15, 12, 26, 32, 47, 54]
Output :
[2, 2, 12, 14, 14, 15, 15, 16, 20, 23, 
26, 32, 47, 48, 52, 54]

Without repetition
Input : 
lst1 = [23, 15, 2, 14, 14, 16, 20 ,52]
lst2 = [2, 48, 15, 12, 26, 32, 47, 54]
Output :
[32, 2, 12, 14, 15, 16, 48, 47, 20, 52, 54, 23, 26]

Union of three lists
Input : 
lst1 = [23, 15, 2, 14, 14, 16, 20 ,52]
lst2 = [2, 48, 15, 12, 26, 32, 47, 54]
lst3 = [4, 78, 5, 6, 9, 25, 64, 32, 59]
Output :
[32, 64, 2, 4, 5, 6, 9, 12, 14, 15, 16, 
48, 47, 78, 20, 52, 54, 23, 25, 26, 59]

```

**保持重复**

我们可以简单地使用**加“+”运算符**将两个列表组合成一个。这将反映重复。

```py
# Python program to illustrate union
# Maintained repetition 
def Union(lst1, lst2):
    final_list = lst1 + lst2
    return final_list

# Driver Code
lst1 = [23, 15, 2, 14, 14, 16, 20 ,52]
lst2 = [2, 48, 15, 12, 26, 32, 47, 54]
print(Union(lst1, lst2))
```

输出:

```py
[23, 15, 2, 14, 14, 16, 20, 52, 2, 48, 15, 
12, 26, 32, 47, 54]

```

**保持重复和秩序**

为了保持新列表中的出现顺序，我们需要使用 **sorted()函数**，将两个列表的相加(加上 operated，如前一个问题)作为参数。

```py
# Python program to illustrate union
# Maintained repetition and order 
def Union(lst1, lst2):
    final_list = sorted(lst1 + lst2)
    return final_list

# Driver Code
lst1 = [23, 15, 2, 14, 14, 16, 20 ,52]
lst2 = [2, 48, 15, 12, 26, 32, 47, 54]
print(Union(lst1, lst2))
```

输出:

```py
[2, 2, 12, 14, 14, 15, 15, 16, 20, 23, 26, 32, 47, 48, 52, 54]

```

**不重复**

为了从初始列表中去除所有重复的元素，我们分别在两个列表上使用 **set()函数**。然后，我们使用“+”运算符添加它们，并作为新列表传递。

```py
# Python program to illustrate union
# Without repetition 
def Union(lst1, lst2):
    final_list = list(set(lst1) | set(lst2))
    return final_list

# Driver Code
lst1 = [23, 15, 2, 14, 14, 16, 20 ,52]
lst2 = [2, 48, 15, 12, 26, 32, 47, 54]
print(Union(lst1, lst2))
```

输出:

```py
[32, 2, 12, 14, 15, 16, 48, 47, 20, 
52, 54, 23, 26]

```

**两个以上列表**

我们也可以将两个以上的列表合并。这可以通过同时使用 **set()和 union()函数**来有效完成，如下例所示。这也照顾到了重复和防止他们。

```py
# Python program to illustrate union
# Union of three lists
def Union(lst1, lst2, lst3):
    final_list = list(set().union(lst1, lst2, lst3))
    return final_list

# Driver Code
lst1 = [23, 15, 2, 14, 14, 16, 20 ,52]
lst2 = [2, 48, 15, 12, 26, 32, 47, 54]
lst3 = [4, 78, 5, 6, 9, 25, 64, 32, 59]
print(Union(lst1, lst2, lst3))
```

输出:

```py
[32, 64, 2, 4, 5, 6, 9, 12, 14, 15, 16, 
48, 47, 78, 20, 52, 54, 23, 25, 26, 59]

```