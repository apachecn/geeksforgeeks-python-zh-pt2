# Python–其他列表中 K 元素的最大值

> 原文:[https://www . geesforgeks . org/python-其他列表中最大 k 元素数/](https://www.geeksforgeeks.org/python-maximum-of-k-element-in-other-list/)

给定两个列表，提取对应列表中 K 相似元素的最大值。

> **输入** : test_list1 = [4，3，6，2，8]，test_list2 = [3，6，3，4，3]，K = 3
> **输出** : 8
> **解释**:3 对应的元素为，4，6，8，最大。是 8。
> **输入** : test_list1 = [10，3，6，2，8]，test_list2 = [5，6，5，4，5]，K = 5
> **输出** : 10
> **解释**:5 对应的元素为，10，6，8，最大。是 10。

**方法#1:使用 loop + max()**

在这种情况下，我们从列表 1 中提取所有与列表 2 中的 K 相等的元素，然后执行 max()以获得它们的最大值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum of K element in other list
# Using loop + max()

# initializing lists
test_list1 = [4, 3, 6, 2, 9]
test_list2 = [3, 6, 3, 4, 3]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing K
K = 3

res = []
for idx in range(len(test_list1)):

    # checking for K in 2nd list
    if test_list2[idx] == K :
        res.append(test_list1[idx])

# getting Maximum element
res = max(res)

# printing result
print("Extracted Maximum element : " + str(res))
```

**Output**

```
The original list 1 is : [4, 3, 6, 2, 9]
The original list 2 is : [3, 6, 3, 4, 3]
Extracted Maximum element : 9
```

**方法二:列表理解+ max() + zip()**

在本文中，我们使用 zip()执行元素配对任务，并且是使用列表理解提供的单行解决方案。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum of K element in other list
# Using list comprehension + max() + zip()

# initializing lists
test_list1 = [4, 3, 6, 2, 9]
test_list2 = [3, 6, 3, 4, 3]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing K
K = 3

# one liner to solve this problem
res = max([sub1 for sub1, sub2 in zip(test_list1, test_list2) if sub2 == K])

# printing result
print("Extracted Maximum element : " + str(res))
```

**Output**

```
The original list 1 is : [4, 3, 6, 2, 9]
The original list 2 is : [3, 6, 3, 4, 3]
Extracted Maximum element : 9
```