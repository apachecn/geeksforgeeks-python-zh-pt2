# Python–按 K 修剪元组

> 原文:[https://www.geeksforgeeks.org/python-trim-tuples-by-k/](https://www.geeksforgeeks.org/python-trim-tuples-by-k/)

给定元组列表，用 k 修剪每个元组

**示例:**

> **输入** : test_list = [(5，3，2，1，4)，(3，4，9，2，1)，(9，1，2，3，5)，(4，8，2，1，7)]，K = 2
> **输出** : [(2，，，(9)、(2)、(2)、(2)，]
> **说明**:前后各去掉 2 个元素。
> 
> **输入** : test_list = [(5，3，2，1，4)，(3，4，9，2，1)，(9，1，2，3，5)，(4，8，2，1，7)]，K = 1
> **输出** : [(3，2，1)，(4，9，2)，(1，2，3)，(8，2，1)]
> **解释**:前后各去掉 1 个元素。

**方法#1:使用循环+切片**

在这种情况下，我们通过使用切片来省略前后 K 个元素，将元组转换为列表，然后再转换为元组。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Trim tuples by K
# Using loop + slicing

# initializing list
test_list = [(5, 3, 2, 1, 4), (3, 4, 9, 2, 1),
             (9, 1, 2, 3, 5), (4, 8, 2, 1, 7)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

res = []
for ele in test_list:
    N = len(ele)

    # triming elements
    res.append(tuple(list(ele)[K: N - K]))

# printing result
print("Converted Tuples : " + str(res))
```

**输出:**

> 原列表为:[(5，3，2，1，4)，(3，4，9，2，1)，(9，1，2，3，5)，(4，8，2，1，7)]
> 转换后的元组:[(2)、(9)、(2)、(2)、(2)、(2)]

**方法二:使用** [**列表理解+切片**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们以与上述方法类似的方式执行任务，不同之处在于使用列表理解来执行单行任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Trim tuples by K
# Using list comprehension + slicing

# initializing list
test_list = [(5, 3, 2, 1, 4), (3, 4, 9, 2, 1),
             (9, 1, 2, 3, 5), (4, 8, 2, 1, 7)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# one-liner approach to solve problem
res = [tuple(list(ele)[K: len(ele) - K]) for ele in test_list]

# printing result
print("Converted Tuples : " + str(res))
```

**输出:**

> 原列表为:[(5，3，2，1，4)，(3，4，9，2，1)，(9，1，2，3，5)，(4，8，2，1，7)]
> 转换后的元组:[(2)、(9)、(2)、(2)、(2)、(2)]