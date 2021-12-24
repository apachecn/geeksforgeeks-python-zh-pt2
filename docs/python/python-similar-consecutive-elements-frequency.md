# Python–相似连续元素频率

> 原文:[https://www . geesforgeks . org/python-相似-连续-元素-频率/](https://www.geeksforgeeks.org/python-similar-consecutive-elements-frequency/)

有时候，在使用 Python 时，我们会遇到一个问题，那就是我们必须找到连续出现的元素。这个问题在学校编程和数据工程中都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以解决这个问题的蛮力方法。在这种情况下，我们迭代循环并计数，直到得到其他数字。

```
# Python3 code to demonstrate 
# Similar Consecutive elements frequency
# using loop

# initializing list 
test_list = [2, 2, 3, 3, 3, 3, 4, 4, 4]

# printing original list
print ("The original list is : " + str(test_list))

# Similar Consecutive elements frequency
# using loop
res = []
count = 1
for ele in range(0, len(test_list) -1):
    if test_list[ele] != test_list[ele + 1]:
        res.append((test_list[ele], count))
        count = 1
    else :
        count = count + 1
res.append((test_list[len(test_list) -1], count))

# printing result 
print ("The consecutive element frequency is : " + str(res))
```

**Output :**

```
The original list is : [2, 2, 3, 3, 3, 3, 4, 4, 4]
The consecutive element frequency is : [(2, 2), (3, 4), (4, 3)]

```