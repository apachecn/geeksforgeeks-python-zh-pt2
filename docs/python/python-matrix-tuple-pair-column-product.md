# Python |矩阵元组对列积

> 原文:[https://www . geesforgeks . org/python-matrix-tuple-pair-column-product/](https://www.geeksforgeeks.org/python-matrix-tuple-pair-column-product/)

有时，我们会遇到一个问题，我们处理一个复杂类型的矩阵列积，其中我们被赋予一个元组，我们需要执行其相似元素的乘积。这在机器学习领域有很好的应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`zip()` +列表理解**
这个问题可以通过使用列表理解来解决，该列表理解可以执行列乘积逻辑，并且 zip 函数用于绑定元素作为结果，并且在垂直乘积时也是如此。

```
# Python3 code to demonstrate
# Matrix Tuple pair Column product
# using list comprehension + zip()

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# initializing list 
test_list = [[(1, 4), (2, 3), (5, 2)], [(3, 7), (1, 9), (10, 5)]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + zip()
# Matrix Tuple pair Column product
res = [tuple(prod(j) for j in zip(*i)) for i in zip(*test_list)]

# print result
print("The product of columns of tuple list : " + str(res))
```

**Output :**

```
The original list : [[(1, 4), (2, 3), (5, 2)], [(3, 7), (1, 9), (10, 5)]]
The product of columns of tuple list : [(3, 28), (2, 27), (50, 10)]

```