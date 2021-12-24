# Python |测试虚假列表

> 原文:[https://www.geeksforgeeks.org/python-test-for-false-list/](https://www.geeksforgeeks.org/python-test-for-false-list/)

有时，我们需要检查一个列表是否完全为真或假，这些情况在开发阶段之后的测试中更常见。因此，了解这一切是必要和有用的。让我们讨论一下实现这一点的某些方法。

**方法#1:天真方法**
在天真方法中，我们只是运行一个从 beg 到列表末尾的循环，并手动检查每个值。这是执行此特定任务的最基本方式。

```py
# Python3 code to demonstrate 
# to check for False list 
# using naive method

# initializing list  
test_list = [False, False, False, False]

# printing original list
print ("The original list is : " + str(test_list))

flag = 0

# using naive method 
# to check for False list 
for i in test_list :
    if i == True :
        flag = 1
        break

# printing result
print ("Is List completely false ? : " +  str(bool(not flag)))
```

**Output:**

```py
The original list is : [False, False, False, False]
Is List completely false ? : True

```