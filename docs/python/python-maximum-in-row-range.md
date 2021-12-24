# Python–行范围内的最大值

> 原文:[https://www.geeksforgeeks.org/python-maximum-in-row-range/](https://www.geeksforgeeks.org/python-maximum-in-row-range/)

给定一个范围和一个矩阵，从该范围的行中提取最大元素。

> **输入** : test_list = [[4，3，6]，[9，1，3]，[4，5，2]，[9，10，3]，[5，9，12]，[3，14，2]]，I，j = 2，5
> **输出** : 12
> **解释**:检查第 2，3，4 行，最大元素为 12。
> 
> **输入** : test_list = [[4，3，6]，[9，1，3]，[4，5，2]，[9，10，3]，[5，9，12]，[3，14，2]]，I，j = 1，4
> **输出** : 10
> **解释**:检查第 1，2，3 行，最大元素为 10。

**方法#1:使用**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+**[**切片**](https://www.geeksforgeeks.org/python-list-slicing/)

在这种情况下，我们执行对必须找到最大值的行进行切片的任务，然后使用 max()为每一行找到最大值，并应用另一个 max()来获取提取元素的最大值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum in Rows Range
# Using max() + slicing

# initializing list
test_list = [[4, 3, 6], [9, 1, 3], [4, 5, 2],
             [9, 10, 3], [5, 9, 12], [3, 14, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 2, 4

res = 0
for idx in range(i, j):

    # getting max in range
    res = max(max(test_list[idx]), res)

# printing result
print("The maximum element in row range ? : " + str(res))
```

**输出:**

> 原列表为:[[4，3，6]，[9，1，3]，[4，5，2]，[9，10，3]，[5，9，12]，[3，14，2]]
> 行范围最大元素？: 10

**方法二:使用 max() +** [**切片+列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用列表理解来执行与上面类似的任务，为这个操作提供一个衬垫。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum in Rows Range
# Using max() + slicing + list comprehension

# initializing list
test_list = [[4, 3, 6], [9, 1, 3], [4, 5, 2],
             [9, 10, 3], [5, 9, 12], [3, 14, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 2, 4

# getting max of maximum of sub lists
res = max([max(test_list[idx]) for idx in range(i, j)])

# printing result
print("The maximum element in row range ? : " + str(res))
```

**输出:**

> 原列表为:[[4，3，6]，[9，1，3]，[4，5，2]，[9，10，3]，[5，9，12]，[3，14，2]]
> 行范围最大元素？: 10