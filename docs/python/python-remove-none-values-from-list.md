# Python |从列表中删除无值

> 原文:[https://www . geesforgeks . org/python-remove-none-values-from-list/](https://www.geeksforgeeks.org/python-remove-none-values-from-list/)

由于机器学习的即将到来，现在的重点已经转移到比以往任何时候都更好地处理*无*值，这背后的原因是，在将数据输入到进一步的技术中执行之前，这是数据预处理的关键步骤。因此，从本质上和知识上消除*无*价值观是必须的。让我们讨论实现这一点的某些方法。

**方法#1:天真方法**
在天真方法中，我们遍历整个列表，并将所有过滤后的非无值追加到一个新列表中，从而准备好执行后续操作。

```
# Python3 code to demonstrate 
# removing None values in list
# using naive method 

# initializing list
test_list = [1, None, 4, None, None, 5, 8, None]

# printing original list 
print ("The original list is : " + str(test_list))

# using naive method 
# to remove None values in list
res = []
for val in test_list:
    if val != None :
        res.append(val)

# printing result
print ("List after removal of None values : " +  str(res))
```

**Output:**

```
The original list is : [1, None, 4, None, None, 5, 8, None]
List after removal of None values : [1, 4, 5, 8]

```