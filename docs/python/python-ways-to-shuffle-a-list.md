# Python |洗牌方法

> 原文:[https://www . geesforgeks . org/python-洗牌方法-a-list/](https://www.geeksforgeeks.org/python-ways-to-shuffle-a-list/)

打乱一系列数字一直是一个有用的工具，这个问题也出现在许多公司的招聘面试中。知道多种方法来实现这一点总是有好处的。让我们讨论一下实现这一点的某些方法。
**方法# 1:**[**Fisher–Yates shuffle Algorithm**](https://www.geeksforgeeks.org/shuffle-a-given-array-using-fisher-yates-shuffle-algorithm/)
这是 python 中主要用来对数字序列进行洗牌的著名算法之一。这个算法只是取较高的索引值，并将其与当前值交换，这个过程循环重复，直到列表结束。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# shuffle a list
# using Fisher–Yates shuffle Algorithm

import random

# initializing list
test_list = [1, 4, 5, 6, 3]

# Printing original list
print ("The original list is : " + str(test_list))

# using Fisher–Yates shuffle Algorithm
# to shuffle a list
for i in range(len(test_list)-1, 0, -1):

    # Pick a random index from 0 to i
    j = random.randint(0, i + 1)

    # Swap arr[i] with the element at random index
    test_list[i], test_list[j] = test_list[j], test_list[i]

# Printing shuffled list
print ("The shuffled list is : " +  str(test_list))
```

**Output:** 

```py
The original list is : [1, 4, 5, 6, 3]
The shuffled list is : [4, 3, 1, 5, 6]
```

**方法 2 :** 使用 random.shuffle()
这是最推荐的洗牌方法。Python 在它的随机库中提供了这个内置的函数，可以就地打乱列表。这样做的缺点是列表排序在这个过程中丢失了。对于选择节省时间和精力的开发人员非常有用。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# shuffle a list
# using random.shuffle()

import random

# initializing list
test_list = [1, 4, 5, 6, 3]

# Printing original list
print ("The original list is : " + str(test_list))

# using random.shuffle()
# to shuffle a list
random.shuffle(test_list)

# Printing shuffled list
print ("The shuffled list is : " +  str(test_list))
```

**Output:** 

```py
The original list is : [1, 4, 5, 6, 3]
The shuffled list is : [5, 6, 4, 3, 1]
```

**方法#3 :** 使用 random.sample()
这是一个相当有用的函数，比上面使用的 shuffle 方法在创建新的洗牌列表并返回而不是打乱原始列表的顺序方面更好。这在我们要求保留原始列表的情况下非常有用。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# shuffle a list
# using random.sample()

import random

# initializing list
test_list = [1, 4, 5, 6, 3]

# Printing original list
print ("The original list is : " + str(test_list))

# using random.sample()
# to shuffle a list
res = random.sample(test_list, len(test_list))

# Printing shuffled list
print ("The shuffled list is : " +  str(res))
```

**Output:** 

```py
The original list is : [1, 4, 5, 6, 3]
The shuffled list is : [5, 3, 6, 1, 4]
```

**方法 4:**

在这种方法中，我们随机选择一个索引，并将该索引处的元素添加到列表中。

## 蟒蛇 3

```py
import random

# Assign array
arr = [1, 2, 3, 4, 5, 6]

# Display original array
print("Original List: ", arr)

# Get length of List
n = len(arr)

#repeat the following for n number of times
for i in range(n):
    #select an index randomly
    j = random.randint(0, n-1)
    #delete the element at that index.
    element=arr.pop(j)
    #now append that deleted element to the list
    arr.append(element)
print("Shuffled List: ",arr)
```

**Output**

```py
Original List:  [1, 2, 3, 4, 5, 6]
Shuffled List:  [4, 5, 3, 2, 6, 1]
```