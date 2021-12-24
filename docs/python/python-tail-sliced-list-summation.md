# Python |尾部切片列表求和

> 原文:[https://www . geesforgeks . org/python-tail-sliced-list-summary/](https://www.geeksforgeeks.org/python-tail-sliced-list-summation/)

我们经常会遇到这样的情况，我们需要通过截断列表的最后一个元素来减小列表的大小，并执行剩余列表求和。当我们需要优化内存时，就会出现这个特殊的问题。这在日常编程中有其应用，有时我们需要得到所有相似大小的列表。让我们讨论执行这项任务的某些方法。
**方法#1:使用 len() +列表切片+ sum()**
列表切片可以执行这个特定的任务，在这个任务中，我们只需将列表中的第一个 len(列表)–K 个元素切片，从而移除最后的 K 个元素。使用 sum()执行尾部求和的任务。

## 蟒蛇 3

```
# Python code to demonstrate
# Tail Sliced List Summation
# using len() + list slicing + sum()

# initializing list
test_list = [1, 4, 6, 3, 5, 8]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K
K = 3

# using len() + list slicing + sum()
# Tail Sliced List Summation
res = sum(test_list[: len(test_list) - K])

# printing result
print ("The tail removed list summation : " + str(res))
```

**Output : **

```
The original list is : [1, 4, 6, 3, 5, 8]
The tail removed list summation : 11
```

**方法 2:使用负列表切片+ sum()**
我们可以使用负列表切片来执行这个特定的任务，在负列表切片中，我们开始从列表的最后一个索引中移除元素，从而从最后一个索引中移除所有的 K 个元素。如果要求删除 0 个元素，我们将无删除。使用 sum()执行尾部求和的任务。

## 蟒蛇 3

```
# Python code to demonstrate
# Tail Sliced List Summation
# using negative list slicing + sum()

# initializing list
test_list = [1, 4, 6, 3, 5, 8]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K
K = 3

# using negative list slicing + sum()
# Tail Sliced List Summation
res = sum(test_list[: -K or None])

# printing result
print ("The tail removed list summation : " + str(res))
```

**Output : **

```
The original list is : [1, 4, 6, 3, 5, 8]
The tail removed list summation : 11
```