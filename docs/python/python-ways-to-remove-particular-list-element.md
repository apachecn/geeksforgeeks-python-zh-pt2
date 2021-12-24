# 在 Python 中移除特定列表元素的方法

> 原文:[https://www . geesforgeks . org/python-移除特定列表元素的方法/](https://www.geeksforgeeks.org/python-ways-to-remove-particular-list-element/)

[List](https://www.geeksforgeeks.org/python-list/) 是一个重要的容器，几乎用于日常编程和网络开发的每个代码中。它用得越多，就越需要掌握它，因此对其操作的了解是必要的。

让我们看看移除特定列表元素的不同方法。

**方法一:使用`[remove()](https://www.geeksforgeeks.org/python-list-remove/)`**
`**remove()**`可以执行列表元素的移除任务。它的拆除是就地进行的，不需要额外的空间。但它面临的缺点是，它只是从列表中删除了第一个匹配项。所有其他事件不会被删除，因此只有当列表不包含重复项时才有用。

```py
# Python code to demonstrate
# element removal in list
# using remove() method

test_list1 = [1, 3, 4, 6, 3]
test_list2 = [1, 4, 5, 4, 5]

# Printing initial list
print ("The list before element removal is : " 
                            + str(test_list1))

# using remove() to remove list element3
test_list1.remove(3)

# Printing list after removal
# only first occurrence deleted
print ("The list after element removal is : "
                           + str(test_list1))
```

输出:

```py
The list before element removal is : [1, 3, 4, 6, 3]
The list after element removal is : [1, 4, 6, 3]
```

**方法 2:使用`[set.disard()](https://www.geeksforgeeks.org/python-remove-discard-sets/)`**
`**set.disard()**`可以执行列表元素的移除任务。它的拆除是就地进行的，不需要额外的空间。列表首先被转换为集合，因此其他副本被删除，列表排序也被牺牲。因此，当我们需要保留订单或需要保留副本时，这不是一个好主意。

```py
# Python code to demonstrate
# element removal in list
# using discard() method

test_list1 = [1, 3, 4, 6, 3]
test_list2 = [1, 4, 5, 4, 5]

# Printing initial list
print ("The list before element removal is : " 
                             + str(test_list2))

# using discard() to remove list element 4
test_list2 = set(test_list2)
test_list2.discard(4)

test_list2 = list(test_list2)

# Printing list after removal
# removes element as distinct initially
print ("The list after element removal is : " 
                           + str(test_list2))
```

**输出:**

```py
The list before element removal is : [1, 4, 5, 4, 5]
The list after element removal is : [1, 5]
```

**方法#3:使用 Lambda 函数+ `filter()`**
Lambda 函数一直是一个有用的工具，因此只需 1 行就可以完成艰巨的任务。这些也可以执行这个特殊的任务。缺点是它们不在原位，需要额外的空间或需要覆盖。它实际上构建了一个新的列表，并过滤掉了所有必需的元素。它删除元素的所有出现。

```py
# Python code to demonstrate
# element removal in list
# using filter() + Lambda function

test_list1 = [1, 3, 4, 6, 3]
test_list2 = [1, 4, 5, 4, 5]

# Printing initial list
print ("The list before element removal is : "
                            + str(test_list1))

# using filter() + Lambda function 
# to remove list element 3
test_list1 = list(filter(lambda x: x != 3, test_list1))

# Printing list after removal
print ("The list after element removal is : " 
                           + str(test_list1))
```

**输出:**

```py
The list before element removal is : [1, 3, 4, 6, 3]
The list after element removal is : [1, 4, 6]
```

**方法#4:使用列表理解**
列表理解是执行类似于 lambda 函数执行的任务的更简单的方法。它有同样的缺点，不在现场，也需要额外的空间或覆盖。最好是不要求 `filter()`去执行。它删除元素的所有出现。

```py
# Python code to demonstrate
# element removal in list
# using List Comprehension

test_list1 = [1, 3, 4, 6, 3]
test_list2 = [1, 4, 5, 4, 5]

# Printing initial list
print ("The list before element removal is : "
                            + str(test_list2))

# using List Comprehension
# to remove list element 4
test_list2 = [x for x in test_list2 if x != 4]

# Printing list after removal
print ("The list after element removal is : " 
                           + str(test_list2))
```

**输出:**

```py
The list before element removal is : [1, 4, 5, 4, 5]
The list after element removal is : [1, 5, 5]

```

**方法 5:使用 pop()**
使用带列表索引的 pop 方法将元素弹出列表

```py
# Python code to demonstrate
# element removal in list
# using pop() method

test_list1 = [1, 3, 4, 6, 3]

# Printing initial list
print ("The list before element removal is : "
                            + str(test_list1))

rmv_element = 4

# using pop()
# to remove list element 4
if rmv_element in test_list1:
    test_list1.pop(test_list1.index(rmv_element))

# Printing list after removal
print ("The list after element removal is : " 
                           + str(test_list1))

# Added by Paras Jain(everythingispossible)
```

**输出:**

```py
The list before element removal is : [1, 3, 4, 6, 3]
The list after element removal is : [1, 3, 6, 3]

```