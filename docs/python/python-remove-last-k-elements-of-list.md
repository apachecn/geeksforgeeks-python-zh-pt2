# Python |移除列表最后 K 个元素

> 原文:[https://www . geesforgeks . org/python-remove-last-k-elements-of-list/](https://www.geeksforgeeks.org/python-remove-last-k-elements-of-list/)

我们经常会遇到这样的情况，我们需要通过截断列表最后的 *k* 元素来减小列表的大小。当我们需要优化内存时，就会出现这个特殊的问题。这在日常编程中有其应用，有时我们需要得到所有相似大小的列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用`len() + list slicing`**
列表切片可以执行这个特殊的任务，在这个任务中，我们只需将第一个*透镜(列表)–K*元素切片到列表中，从而移除最后的 K 个元素。

```
# Python code to demonstrate 
# remove last K elements
# using len() + list slicing

# initializing list  
test_list = [1, 4, 6, 3, 5, 8]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 3

# using len() + list slicing
# remove last K elements
res = test_list[: len(test_list) - K]

# printing result 
print ("The list after removing last K elements : " +  str(res))
```

**Output:**

```
The original list is : [1, 4, 6, 3, 5, 8]
The list after removing last K elements : [1, 4, 6]

```

**方法 2:使用负列表切片**
我们可以使用负列表切片来执行这个特定的任务，在负列表切片中，我们开始从列表的最后一个索引中移除元素，从而从最后一个中移除所有的 *K* 元素。如果要求移除 0 个元素，我们移除*无*。

```
# Python code to demonstrate 
# remove last K elements
# using negative list slicing

# initializing list  
test_list = [1, 4, 6, 3, 5, 8]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 3

# using negative list slicing
# remove last K elements
res = test_list[: -K or None]

# printing result 
print ("The list after removing last K elements : " +  str(res))
```

**Output:**

```
The original list is : [1, 4, 6, 3, 5, 8]
The list after removing last K elements : [1, 4, 6]

```