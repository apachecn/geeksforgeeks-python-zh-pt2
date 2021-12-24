# Python 程序，用于从元组列表中找到所有元素都可以被 K 整除的元组

> 原文:[https://www . geesforgeks . org/python-program-to-find-元组-具有所有元素-可被 k 整除-从元组列表/](https://www.geeksforgeeks.org/python-program-to-find-tuples-which-have-all-elements-divisible-by-k-from-a-list-of-tuples/)

给定元组列表。任务是提取所有元素可被 k 整除的元组。

> **输入** : test_list = [(6，24，12)，(60，12，6)，(12，18，21)]，K = 6
> **输出** : [(6，24，12)，(60，12，6)]
> **解释**:两个元组都有 6 的所有元素倍数。
> 
> **输入** : test_list = [(6，24，12)，(60，10，5)，(12，18，21)]，K = 5
> **输出** : [(60，10，5)]
> **解释**:提取的 5 元组的倍数。

**方法一:使用列表理解+ all()**

在这种情况下，我们使用 [all()](https://www.geeksforgeeks.org/any-all-in-python/) 来测试所有元素是否为 K 的倍数，并使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)来迭代所有元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# K Multiple Elements Tuples
# Using list comprehension + all()

# initializing list
test_list = [(6, 24, 12), (7, 9, 6), (12, 18, 21)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

# all() used to filter elements
res = [sub for sub in test_list if all(ele % K == 0 for ele in sub)]

# printing result
print("K Multiple elements tuples : " + str(res))
```

**Output**

```py
The original list is : [(6, 24, 12), (7, 9, 6), (12, 18, 21)]
K Multiple elements tuples : [(6, 24, 12)]

```

**方法 2:使用滤镜()+ lambda + all()**

在这种情况下，我们使用 filter() + lambda 和 all()提供的逻辑执行过滤任务，就像上面的方法一样。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# K Multiple Elements Tuples
# Using filter() + lambda + all()

# initializing list
test_list = [(6, 24, 12), (7, 9, 6), (12, 18, 21)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

# filter() + lambda for filter operation
res = list(filter(lambda sub: all(ele % K == 0 for ele in sub), test_list))

# printing result
print("K Multiple elements tuples : " + str(res))
```

**Output**

```py
The original list is : [(6, 24, 12), (7, 9, 6), (12, 18, 21)]
K Multiple elements tuples : [(6, 24, 12)]

```