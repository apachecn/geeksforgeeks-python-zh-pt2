# Python–按 K 倍数排序行

> 原文:[https://www . geesforgeks . org/python-sort-row-by-k-multiples/](https://www.geeksforgeeks.org/python-sort-row-by-k-multiples/)

给定一个矩阵，按行中 K 的倍数进行行排序。

> **输入** : test_list = [[3，4，8，1]，[12，32，4，16]，[1，2，3，4]，[9，7，5]]，K = 4
> **输出** : [[9，7，5]，[1，2，3，4]，[3，4，8，1]，[12，32，4，16]]
> **解释**:0<1【T7
> 
> **输入** : test_list = [[3，4，8，1]，[12，32，4，16]，[1，2，3，4]，[9，7，5]]，K = 2
> **输出** : [[9，7，5]，[1，2，3，4]，[3，4，8，1]，[12，32，4，16]]
> **解释** : 0 < 2 = 2

**方法#1:使用 sort() + %运算符+ len()**

在本例中，我们使用%运算符测试多个，然后通过获取筛选元素的长度来计算计数，提供给执行行就地排序的 key to sort()。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort row by K multiples
# Using sort() + % operator + len()

# checking for multiples count

def k_mul(row):
    return len([ele for ele in row if ele % K == 0])

# initializing list
test_list = [[3, 4, 8, 1], [12, 32, 4, 16], [1, 2, 3, 4], [9, 7, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

# performing sort
test_list.sort(key=k_mul)

# printing result
print("Sorted result : " + str(test_list))
```

**输出:**

> 原始列表为:[[3，4，8，1]，[12，32，4，16]，[1，2，3，4]，[9，7，5]]
> 排序结果:[[9，7，5]，[1，2，3，4]，[3，4，8，1]，[12，32，4，16]]

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，排序是使用 sorted()完成的，len()用于获取所有 K 的倍数的长度，就像上面的方法一样。lambda 函数提供了执行逻辑注入的单一语句替代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort row by K multiples
# Using sorted() + lambda + len()

# initializing list
test_list = [[3, 4, 8, 1], [12, 32, 4, 16], [1, 2, 3, 4], [9, 7, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

# performing sort using sorted()
# lambda avoiding external function call
res = sorted(test_list, key=lambda row: len(
    [ele for ele in row if ele % K == 0]))

# printing result
print("Sorted result : " + str(res))
```

**输出:**

> 原始列表为:[[3，4，8，1]，[12，32，4，16]，[1，2，3，4]，[9，7，5]]
> 排序结果:[[9，7，5]，[1，2，3，4]，[3，4，8，1]，[12，32，4，16]]