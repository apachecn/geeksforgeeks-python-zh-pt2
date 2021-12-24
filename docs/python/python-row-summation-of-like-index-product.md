# Python–同类指数积的行求和

> 原文:[https://www . geesforgeks . org/python-row-summary-of-like-index-product/](https://www.geeksforgeeks.org/python-row-summation-of-like-index-product/)

给定一个矩阵和元素列表，对于每一行，提取带有参数列表的元素乘积的总和。

> **输入** : test_list = [[4，5]，[1，5]，[8，2]]，mul_list = [5，2，3]
> **输出** : [30，15，44]
> **解释**:第一行，(4*5) + (5*2) = 30，作为结果列表第一个元素的值。这样计算每个元素。
> 
> **输入** : test_list = [[4，5，8，2]]，mul_list = [5，2，3，9]
> **输出**:【72】
> **解释**:与上述方法计算类似。只有一个元素作为单行。

**方法#1:使用循环**
这是蛮力的方式解决这个问题。在这种情况下，我们执行每行的迭代，并使用循环的蛮力方法在乘积中执行所需的求和。

```
# Python3 code to demonstrate working of 
# Row Summation of Like Index Product
# Using loop

# initializing list
test_list = [[3, 4, 5], [1, 7, 5], [8, 1, 2]] 

# printing original list
print("The original list is : " + str(test_list))

# initializing mul list  
mul_list = [5, 2, 3]

# Using loop
res = []
for sub in test_list:
    sum = 0
    for idx, ele in enumerate(sub):

        # performing summation of product with list elements
        sum = sum + (ele * mul_list[idx])

    # adding each row sum
    res.append(sum)

# printing result 
print("List after multiplication : " + str(res))
```

**Output :**

```
The original list is : [[3, 4, 5], [1, 7, 5], [8, 1, 2]]
List after multiplication : [38, 34, 48]

```

**方法 2:使用`map() + sum() + zip() + lambda`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 sum()执行求和任务，zip()用于将乘法列表与行值进行映射，并将逻辑封装并扩展到每行，而其元素使用 lambda 和 map()。

```
# Python3 code to demonstrate working of 
# Row Summation of Like Index Product
# Using map() + sum() + zip() + lambda

# initializing list
test_list = [[3, 4, 5], [1, 7, 5], [8, 1, 2]] 

# printing original list
print("The original list is : " + str(test_list))

# initializing mul list  
mul_list = [5, 2, 3]

# Using map() + sum() + zip() + lambda
# Performing product in inner map, by zipping with elements list, and sum at outer map() used.
res = list(map(sum, (map(lambda ele: ([x * y for x, y in zip(
                              ele, mul_list)]), test_list))))

# printing result 
print("List after multiplication : " + str(res))
```

**Output :**

```
The original list is : [[3, 4, 5], [1, 7, 5], [8, 1, 2]]
List after multiplication : [38, 34, 48]

```