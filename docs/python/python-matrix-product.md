# Python |矩阵产品

> 原文:[https://www.geeksforgeeks.org/python-matrix-product/](https://www.geeksforgeeks.org/python-matrix-product/)

获得列表的乘积是一个很常见的问题，并且已经被处理和讨论了很多次，但是有时，我们需要改进它和总乘积，即也包括嵌套列表的乘积。让我们试着得到总的产品并解决这个特殊的问题。

**方法#1:使用列表理解+循环**
我们可以使用列表理解作为常规循环的潜在速记来解决这个问题，我们可以使用常规循环来执行这个特定的任务。我们只是迭代并乘积嵌套列表，最后使用函数返回累积乘积。

```
# Python3 code to demonstrate
# Matrix Product
# Using list comprehension + loop

# getting Product
def prod(val) :
    res = 1 
    for ele in val:
        res *= ele
    return res 

# initializing list
test_list = [[1, 4, 5], [7, 3], [4], [46, 7, 3]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + loop
# Matrix Product
res = prod([ele for sub in test_list for ele in sub])

# print result
print("The total element product in lists is : " + str(res))
```

**Output :**

```
The original list : [[1, 4, 5], [7, 3], [4], [46, 7, 3]]
The total element product in lists is : 1622880

```