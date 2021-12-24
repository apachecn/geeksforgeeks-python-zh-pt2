# Python |移除前 K 元素

> 原文:[https://www . geesforgeks . org/python-remove-front-k-elements/](https://www.geeksforgeeks.org/python-remove-front-k-elements/)

我们经常遇到需要通过截断列表的第一个元素来减小列表大小的情况。当我们需要优化内存时，就会出现这个特殊的问题。这在日常编程中有其应用，有时我们需要得到所有相似大小的列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用`len()` +列表切片**
列表切片可以执行这个特殊的任务，在这个任务中，我们只需将最后一个镜头(列表)切片——列表中的 K 个元素，从而移除前 K 个元素。

```py
# Python code to demonstrate 
# Remove Front K elements
# using len() + list slicing

# initializing list 
test_list = [1, 4, 6, 3, 5, 8]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 3

# using len() + list slicing
# Remove Front K elements
res = test_list[K:]

# printing result 
print ("The list after removing first K elements : " + str(res))
```

**Output :**

```py
The original list is : [1, 4, 6, 3, 5, 8]
The list after removing first K elements : [3, 5, 8]

```