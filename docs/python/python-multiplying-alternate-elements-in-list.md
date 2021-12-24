# Python |列表中的乘法替代元素

> 原文:[https://www . geesforgeks . org/python-乘法-替代-列表中的元素/](https://www.geeksforgeeks.org/python-multiplying-alternate-elements-in-list/)

获取列表乘积的问题非常普遍，我们可能有一天会面临获取替代元素乘积的问题，并获取包含替代元素乘积的 2 个元素的列表。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+列表切片+循环**
使用列表理解的列表切片可以用来执行这个特定的任务。我们可以通过列表理解来获得运行逻辑，列表切片可以通过外部产品功能来切割出备选字符、产品。

```
# Python3 code to demonstrate
# Multiplying Alternate elements in List
# using list comprehension + list slicing

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# initializing list 
test_list = [2, 1, 5, 6, 8, 10]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + list slicing
# Multiplying Alternate elements in List
res = [prod(test_list[i : : 2]) for i in range(len(test_list) // (len(test_list)//2))]

# print result
print("The alternate elements product list : " + str(res))
```

**Output :**

```
The original list : [2, 1, 5, 6, 8, 10]
The alternate elements product list : [80, 60]

```