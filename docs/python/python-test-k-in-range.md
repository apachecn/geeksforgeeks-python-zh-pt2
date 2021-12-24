# Python–测试范围内的 K

> 原文:[https://www.geeksforgeeks.org/python-test-k-in-range/](https://www.geeksforgeeks.org/python-test-k-in-range/)

给定一个列表，测试给定范围内的所有元素是否等于 k

> **输入** : test_list = [2，3，4，4，4，4，6，7，8，2]，I，j = 2，5，K = 4
> **输出** : True
> **解释**:范围内所有元素均为 4。
> 
> **输入** : test_list = [2，3，4，9，4，4，6，7，8，2]，I，j = 2，5，K = 4
> **输出** : False
> **解释**:范围内所有元素都不是 4。

**方法#1:使用** [**任意()**](https://www.geeksforgeeks.org/any-all-in-python/)

在这种情况下，我们检查逻辑的否定是否被发现，检查我们是否得到除了 K 之外的任何元素，我们返回真值的否定以得到实际的结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test K in Range
# Using any()

# initializing list
test_list = [2, 3, 4, 4, 4, 4, 6, 7, 8, 2]

# printing original list
print("The original list is : " + str(test_list))

# initializing Range
i, j = 2, 5

# initializing K 
K = 4

# any() to check if any element other than K present 
# negation gives result 
res = not any(test_list[idx] != K for idx in range(i, j + 1))

# printing result 
print("Are all elements in range K ? : " + str(res))
```

**Output**

```py
The original list is : [2, 3, 4, 4, 4, 4, 6, 7, 8, 2]
Are all elements in range K ? : True

```

**方法 2:使用 all()**

在这种情况下，我们使用 all()检查列表的所需范围内的所有元素是否为 K。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test K in Range
# Using all() 

# initializing list
test_list = [2, 3, 4, 4, 4, 4, 6, 7, 8, 2]

# printing original list
print("The original list is : " + str(test_list))

# initializing Range
i, j = 2, 5

# initializing K 
K = 4

# all() to check all elements to be K 
res = all(test_list[idx] == K for idx in range(i, j + 1))

# printing result 
print("Are all elements in range K ? : " + str(res))
```

**Output**

```py
The original list is : [2, 3, 4, 4, 4, 4, 6, 7, 8, 2]
Are all elements in range K ? : True

```