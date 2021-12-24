# Python |从其他列表中的列表中移除所有值

> 原文:[https://www . geesforgeks . org/python-从列表中删除所有值-存在于其他列表中/](https://www.geeksforgeeks.org/python-remove-all-values-from-a-list-present-in-other-list/)

有时，我们需要执行从存在于另一个列表中的列表中移除所有项目的操作，即，在一个列表中给我们一些无效的数字，这些数字需要从原始列表中移除。让我们讨论一下实现这一点的各种方法。
**方法#1:使用列表理解**
列表理解可以用来在一行中执行简单的方法，因此给出了执行这个特定任务的简单方法。

## 蟒蛇 3

```
# Python 3 code to demonstrate
# to remove elements present in other list
# using list comprehension

# initializing list
test_list = [1, 3, 4, 6, 7]

# initializing remove list
remove_list = [3, 6]

# printing original list
print ("The original list is : " + str(test_list))

# printing remove list
print ("The original list is : " + str(remove_list))

# using list comprehension to perform task
res = [i for i in test_list if i not in remove_list]

# printing result
print ("The list after performing remove operation is : " + str(res))
```

**输出:**

```
The original list is : [1, 3, 4, 6, 7]
The original list is : [3, 6]
The list after performing remove operation is : [1, 4, 7]

```

**方法#2:使用 filter()+lambda**
filter 函数可以与 lambda 一起使用来执行此任务，并创建一个新的过滤列表，其中包含移除元素列表中不存在的所有元素。

## 蟒蛇 3

```
# Python 3 code to demonstrate
# to remove elements present in other list
# using filter() + lambda

# initializing list
test_list = [1, 3, 4, 6, 7]

# initializing remove list
remove_list = [3, 6]

# printing original list
print ("The original list is : " + str(test_list))

# printing remove list
print ("The original list is : " + str(remove_list))

# using filter() + lambda to perform task
res = filter(lambda i: i not in remove_list, test_list)

# printing result
print ("The list after performing remove operation is : " + str(res))
```

**输出:**

```
The original list is : [1, 3, 4, 6, 7]
The original list is : [3, 6]
The list after performing remove operation is : [1, 4, 7]

```

**方法#3:使用 remove()**
remove()也可以执行此任务，但前提是没有获取特定元素的异常处理得当。可以迭代移除列表中的所有元素，并从原始列表中移除这些元素。

## 蟒蛇 3

```
# Python 3 code to demonstrate
# to remove elements present in other list
# using remove()

# initializing list
test_list = [1, 3, 4, 6, 7]

# initializing remove list
remove_list = [3, 6]

# printing original list
print ("The original list is : " + str(test_list))

# printing remove list
print ("The original list is : " + str(remove_list))

# using remove() to perform task
# handled exceptions.
for i in remove_list:
    try:
        test_list.remove(i)
    except ValueError:
        pass

# printing result
print ("The list after performing remove operation is : " + str(test_list))
```

**输出:**

```
The original list is : [1, 3, 4, 6, 7]
The original list is : [3, 6]
The list after performing remove operation is : [1, 4, 7]

```

**方法#4:使用 set()**
set()可用于执行此任务，并创建一个新的过滤列表，其中包含移除元素列表中不存在的所有元素。

## 蟒蛇 3

```
# Python 3 code to demonstrate
# to remove elements present in other list
# using set()

# initializing list
test_list = [1, 3, 4, 6, 7]

# initializing remove list
remove_list = [3, 6]

# printing original list
print ("The original list is : " + str(test_list))

# printing remove list
print ("The original list is : " + str(remove_list))

# using set() to perform task
set1 = set(test_list)
set2 = set(remove_list)
res = list(set1 - set2)

# printing result
print ("The list after performing remove operation is : " + str(res))
```

**输出:**

```
The original list is : [1, 3, 4, 6, 7]
The original list is : [3, 6]
The list after performing remove operation is : [1, 4, 7]

```