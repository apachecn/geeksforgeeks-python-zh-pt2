# Python–乘二列表

> 原文:[https://www.geeksforgeeks.org/python-multiply-two-list/](https://www.geeksforgeeks.org/python-multiply-two-list/)

在许多情况下，人们需要找到两个不同列表的索引乘积。这在日常编程中可能会有应用。让我们讨论执行这项任务的各种方法。

**方法#1:天真的方法**
在这个方法中，我们简单地运行一个循环，并将两个列表元素在相似索引处的乘积附加到新列表中，直到我们到达较小列表的末尾。这是完成这项任务的基本方法。

```py
# Python code to demonstrate 
# Multiplying two lists
# naive method 

# initializing lists
test_list1 = [1, 3, 4, 6, 8]
test_list2 = [4, 5, 6, 2, 10]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using naive method to 
# Multiplying two lists
res_list = []
for i in range(0, len(test_list1)):
    res_list.append(test_list1[i] * test_list2[i])

# printing resultant list 
print ("Resultant list is : " + str(res_list))
```

**Output :**

```py
Original list 1 : [1, 3, 4, 6, 8]
Original list 2 : [4, 5, 6, 2, 10]
Resultant list is : [4, 15, 24, 12, 80]

```