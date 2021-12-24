# Python |在列表中查找数值索引的方法

> 原文:[https://www . geeksforgeeks . org/python-在列表中查找价值指数的方法/](https://www.geeksforgeeks.org/python-ways-to-find-indices-of-value-in-list/)

通常，我们需要找到特定值所在的索引。有很多方法可以实现，使用`index()`等。但有时需要找到一个特定值的所有索引，以防它在列表中多次出现。

让我们讨论在给定列表中找到值的索引的某些方法。

**方法#1:天真方法**

我们可以通过遍历列表并检查该值来完成这个任务，只需在新列表中添加值索引并打印它。这是完成这个任务的基本蛮力方法。

```py
# Python3 code to demonstrate 
# finding indices of values
# using naive method 

# initializing list 
test_list = [1, 3, 4, 3, 6, 7]

# printing initial list 
print ("Original list : " + str(test_list))

# using naive method
# to find indices for 3
res_list = []
for i in range(0, len(test_list)) :
    if test_list[i] == 3 :
        res_list.append(i)

# printing resultant list 
print ("New indices list : " + str(res_list))
```

**Output:**

```py
Original list : [1, 3, 4, 3, 6, 7]
New indices list : [1, 3]

```

**方法 2:使用列表理解**

列表理解只是实现强力任务的速记技术，只是使用较少的代码行来完成任务，因此节省了程序员的时间。

```py
# Python3 code to demonstrate 
# finding indices of values
# using list comprehension 

# initializing list 
test_list = [1, 3, 4, 3, 6, 7]

# printing initial list 
print ("Original list : " + str(test_list))

# using list comprehension
# to find indices for 3
res_list = [i for i in range(len(test_list)) if test_list[i] == 3]

# printing resultant list 
print ("New indices list : " + str(res_list))
```

**Output:**

```py
Original list : [1, 3, 4, 3, 6, 7]
New indices list : [1, 3]

```

**方法三:使用`enumerate()`**
使用`enumerate()`我们可以实现类似的任务，这是比上面略快的手法，因此推荐使用超列表理解手法。

```py
# Python3 code to demonstrate 
# finding indices of values
# using enumerate()

# initializing list 
test_list = [1, 3, 4, 3, 6, 7]

# printing initial list 
print ("Original list : " + str(test_list))

# using enumerate()
# to find indices for 3
res_list = [i for i, value in enumerate(test_list) if value == 3]

# printing resultant list 
print ("New indices list : " + str(res_list))
```

**Output:**

```py
Original list : [1, 3, 4, 3, 6, 7]
New indices list : [1, 3]

```

**方法 4:使用`filter()`**

这是可用于实现该特定任务的另一种方法，`filter()`通常能够执行过滤任务，因此也可在这种情况下用于实现该任务。

```py
# Python3 code to demonstrate 
# finding indices of values
# using filter()

# initializing list 
test_list = [1, 3, 4, 3, 6, 7]

# printing initial list 
print ("Original list : " + str(test_list))

# using filter()
# to find indices for 3
res_list = list(filter(lambda x: test_list[x] == 3, range(len(test_list))))

# printing resultant list 
print ("New indices list : " + str(res_list))
```

**Output:**

```py
Original list : [1, 3, 4, 3, 6, 7]
New indices list : [1, 3]

```