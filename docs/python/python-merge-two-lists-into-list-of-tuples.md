# Python |将两个列表合并成元组列表

> 原文:[https://www . geesforgeks . org/python-merge-two-list-to-list-of-tuples/](https://www.geeksforgeeks.org/python-merge-two-lists-into-list-of-tuples/)

给定两个列表，编写一个 Python 程序将这两个列表合并成元组列表。

**示例:**

```
Input : list1 = [1, 2, 3]
        list2 = ['a', 'b', 'c']
Output : [(1, 'a'), (2, 'b'), (3, 'c')]

Input : list1 = [1, 2, 3, 4]
        list2 = [ 1, 4, 9]
Output : [(1, 1), (2, 4), (3, 9), (4, '')]

```

**方法#1 :** 天真
使用 for 循环将两个列表合并成一个元组列表。但是缺点是两个列表需要有相同的长度。

```
def merge(list1, list2):

    merged_list = [(list1[i], list2[i]) for i in range(0, len(list1))]
    return merged_list

# Driver code
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
print(merge(list1, list2))
```

**Output:**

```
[(1, 'a'), (2, 'b'), (3, 'c')]

```

**方法#2 :** 简单但更有效的
这种方法消除了上面给出的缺点，在两个列表长度不均匀的情况下也能很好地工作。它还为索引错误提供了尝试捕获错误。

```
def merge(list1, list2):

    merged_list = []
    for i in range(max((len(list1), len(list2)))):

        while True:
            try:
                tup = (list1[i], list2[i])
            except IndexError:
                if len(list1) > len(list2):
                    list2.append('')
                    tup = (list1[i], list2[i])
                elif len(list1) < len(list2):
                    list1.append('')
                    tup = (list1[i], list2[i])
                continue

            merged_list.append(tup)
            break
    return merged_list

# Driver code
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
print(merge(list1, list2))
```

**Output:**

```
[(1, 'a'), (2, 'b'), (3, 'c')]

```

**方法#3 :** 使用`zip()`
使用 zip()方法合并两个列表元素，然后类型转换为元组。

```
def merge(list1, list2):

    merged_list = tuple(zip(list1, list2)) 
    return merged_list

# Driver code
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
print(merge(list1, list2))
```

**Output:**

```
((1, 'a'), (2, 'b'), (3, 'c'))

```

**方法#4 :** 使用枚举()，替代 zip()。

此方法使用两个 for 循环来枚举列表并合并这两个列表。

```
def merge(list1, list2):

    merged_list = [(p1, p2) for idx1, p1 in enumerate(list1) 
    for idx2, p2 in enumerate(list2) if idx1 == idx2]
    return merged_list

# Driver code
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
print(merge(list1, list2))
```

**Output:**

```
[(1, 'a'), (2, 'b'), (3, 'c')]

```

**使用`map()`和`lambda`接近#5:** 。

```
# Using map() and lambda
def listOfTuples(l1, l2):
    return list(map(lambda x, y:(x,y), l1, l2))

# Driver Code
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']

print(listOfTuples(list1, list2))
```

**Output:**

```
[(1, 'a'), (2, 'b'), (3, 'c')]

```