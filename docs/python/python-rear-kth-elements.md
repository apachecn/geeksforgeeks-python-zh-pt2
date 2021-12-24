# 蟒蛇皮–后 Kth 元素

> 原文:[https://www.geeksforgeeks.org/python-rear-kth-elements/](https://www.geeksforgeeks.org/python-rear-kth-elements/)

给定一个列表，任务是从后端提取所有的 Kth 元素。

> **输入** : test_list = [3，4，5，2，1]，K = 2
> **输出**:【1，5，3】
> **说明**:从 1 开始从后方提取每 2 个元素。
> 
> **输入**:test _ list =【3，4，5】，K = 1
> **输出**:【5，4，3】
> **说明**:每一个元素都是从 1 开始从后方提取的。

**方法#1:使用循环**
这是解决这个问题的蛮法。在这种情况下，我们反转，然后执行迭代，以获得每个 Kth 多个元素。

```
# Python3 code to demonstrate working of 
# Rear Kth elements
# Using loop

# initializing list
test_list = [3, 5, 7, 9, 10, 2, 8, 6] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# Rear Kth elements
res = []
test_list.reverse()
for idx, ele in enumerate(test_list):

    # Extracting elements divisible by K
    if idx % K == 0:
        res.append(ele)

# printing result 
print("Rear Kth elements : " + str(res))
```

**Output :**

```
The original list is : [3, 5, 7, 9, 10, 2, 8, 6]
Rear Kth elements : [6, 10, 5]

```

**方法 2:使用列表切片**
这是这个问题的速记版解决方案。我们使用列表切片跳过的力量来跳过 Kth 元素，也可以反转它。

```
# Python3 code to demonstrate working of 
# Rear Kth elements
# Using list slicing

# initializing list
test_list = [3, 5, 7, 9, 10, 2, 8, 6] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# Rear Kth elements
# Starting slicing from Rear (-1) and extracting all Kth elements
res = test_list[-1::-K]

# printing result 
print("Rear Kth elements : " + str(res))
```

**Output :**

```
The original list is : [3, 5, 7, 9, 10, 2, 8, 6]
Rear Kth elements : [6, 10, 5]

```