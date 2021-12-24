# Python–测试列表是否包含范围内的元素

> 原文:[https://www . geesforgeks . org/python-test-if-list-contains-in-range 元素/](https://www.geeksforgeeks.org/python-test-if-list-contains-elements-in-range/)

很多时候，在处理数据时，我们会遇到一个问题，那就是我们需要确保一个容器或一个列表只包含一个范围内的元素。这在数据域中有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，如果元素落在范围内，我们就使用 if 条件进行检查，如果我们发现甚至有一个出现在范围外，我们就中断。

```py
# Python3 code to demonstrate 
# Test if List contains elements in Range
# using loop

# Initializing loop 
test_list = [4, 5, 6, 7, 3, 9]

# printing original list 
print("The original list is : " + str(test_list))

# Initialization of range 
i, j = 3, 10

# Test if List contains elements in Range
# using loop
res = True
for ele in test_list:
    if ele < i or ele >= j :
        res = False 
        break

# printing result 
print ("Does list contain all elements in range : " + str(res))
```

**Output :**

```py
The original list is : [4, 5, 6, 7, 3, 9]
Does list contain all elements in range : True

```