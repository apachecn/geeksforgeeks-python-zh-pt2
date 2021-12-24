# Python |垂直打印列表

> 原文:[https://www . geesforgeks . org/python-printing-list-垂直/](https://www.geeksforgeeks.org/python-printing-list-vertically/)

打印清单已经处理过多次了。但是有时我们需要不同的格式来获得列表的输出。这在矩阵转置中也有应用。垂直打印列表在 web 开发中也有应用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用天真法**
天真法可以垂直 vis 打印列表。使用循环并连续打印每个列表的每个索引元素将有助于我们完成这项任务。

```
# Python3 code to demonstrate 
# Vertical list print 
# using naive method 

# initializing list  
test_list = [[1, 4, 5], [4, 6, 8], [8, 3, 10]]

# printing original list
print ("The original list is : " + str(test_list))

# using naive method  
# to print list vertically
for i in range(len(test_list)):
    for x in test_list:
        print(x[i], end =' ')
    print()
```

**输出:**

```
The original list is : [[1, 4, 5], [4, 6, 8], [8, 3, 10]]
1 4 8 
4 6 3 
5 8 10 

```

**方法 2:使用`zip()`**
使用 zip 函数，我们将各个索引处的元素相互映射，然后打印每个元素。这执行垂直打印的任务。

```
# Python3 code to demonstrate 
# Vertical list print 
# using zip()

# initializing list  
test_list = [[1, 4, 5], [4, 6, 8], [8, 3, 10]]

# printing original list
print ("The original list is : " + str(test_list))

# using zip() 
# to print list vertically
for x, y, z in zip(*test_list):
    print(x, y, z)
```

**输出:**

```
The original list is : [[1, 4, 5], [4, 6, 8], [8, 3, 10]]
1 4 8
4 6 3
5 8 10

```