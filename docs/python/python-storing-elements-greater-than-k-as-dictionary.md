# Python–将大于 K 的元素存储为字典

> 原文:[https://www . geesforgeks . org/python-存储元素-大于 k-as-dictionary/](https://www.geeksforgeeks.org/python-storing-elements-greater-than-k-as-dictionary/)

有时，在使用 python 列表时，我们可能会遇到一个问题，即我们需要提取大于 k 的元素。但有时，我们不需要存储双重性，因此在字典中按键值对存储。跟踪字典中出现的数字位置。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们通过检查大于 k 的元素来以字典的形式存储元素。

```py
# Python3 code to demonstrate 
# Storing Elements Greater than K as Dictionary
# using loop

# Initializing list
test_list = [12, 44, 56, 34, 67, 98, 34]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 50

# Storing Elements Greater than K as Dictionary
# using loop
res = dict()
count = 1
for ele in test_list:
    if ele > K:
        res[count] = ele
        count = count + 1

# printing result 
print ("The dictionary after storing elements : " + str(res))
```

**Output :**

```py
The original list is : [12, 44, 56, 34, 67, 98, 34]
The dictionary after storing elements : {1: 56, 2: 67, 3: 98}

```