# Python–移除差异大于 K 的元组

> 原文:[https://www . geeksforgeeks . org/python-remove-元组-具有大于-k 的差异/](https://www.geeksforgeeks.org/python-remove-tuples-with-difference-greater-than-k/)

给定二元组列表，移除差值大于 k 的对

> **输入** : test_list = [(4，8)，(1，7)，(9，12)，(3，12)，(2，10)]，K = 6
> **输出** : [(4，8)，(9，12)，(1，7)]
> **解释**:4(8–4)，3(12–9)和 6 都不大于 6，因此保留。
> 
> **输入** : test_list = [(4，8)，(1，7)，(9，12)，(3，12)，(2，10)]，K = 3
> **输出** : [(9，12)]
> **解释**:3(12–9)不大于 3，因此保留。

**方法一:使用列表理解**

在这种情况下，我们通过使用 *abs()* 测试绝对差值来执行过滤，如果发现小于 K，则保留其，因此大于 K 的差值元组被移除。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove Tuples with difference greater than K
# Using list comprehension

# initializing list
test_list = [(4, 8), (1, 7), (9, 12), (3, 12), (2, 10)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# filtering using list comprehension, checking for smaller than K diff.
res = [sub for sub in test_list if abs(sub[0] - sub[1]) <= K]

# printing result
print("Tuples List after removal : " + str(res))
```

**输出:**

> 原列表为:[(4，8)，(1，7)，(9，12)，(3，12)，(2，10)]
> 去除后的元组列表:[(4，8)，(9，12)]

**方法 2:使用过滤器()+λ+ABS()**

在这种情况下，使用*滤波器()*和*λ*功能执行滤波任务，使用 *abs()* 获得绝对差值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove Tuples with difference greater than K
# Using filter() + lambda + abs()

# initializing list
test_list = [(4, 8), (1, 7), (9, 12), (3, 12), (2, 10)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# Using filter() and lambda function for filtering
res = list(filter(lambda sub: abs(sub[0] - sub[1]) <= K, test_list))

# printing result
print("Tuples List after removal : " + str(res))
```

**输出:**

> 原列表为:[(4，8)，(1，7)，(9，12)，(3，12)，(2，10)]
> 去除后的元组列表:[(4，8)，(9，12)]