# Python |记录索引产品

> 原文:[https://www.geeksforgeeks.org/python-record-index-product/](https://www.geeksforgeeks.org/python-record-index-product/)

有时，在处理记录时，我们会遇到一个问题，即我们需要将元组列表容器中的所有列相乘。这种应用在 web 开发领域很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+列表理解+ `zip()`**
该任务可以使用上述功能的组合来执行。在本文中，我们使用 zip()对相似的索引元素(即列)进行模拟，然后使用列表理解对它们进行迭代，并使用显式函数执行乘积运算。

```
# Python3 code to demonstrate working of
# Record Index Product
# using list comprehension + loop + zip()

# getting Product
def prod(val) :
    res = 1 
    for ele in val:
        res *= ele
    return res 

# initialize list
test_list = [(1, 2, 3), (6, 7, 6), (1, 6, 8)]

# printing original list
print("The original list : " + str(test_list))

# Record Index Product
# using list comprehension + loop + zip()
res = [prod(ele) for ele in zip(*test_list)]

# printing result
print("The Cummulative column product is : " + str(res))
```

**Output :**

```
The original list : [(1, 2, 3), (6, 7, 6), (1, 6, 8)]
The Cummulative column product is : [6, 84, 144]

```