# Python–使用索引列表的元素乘积

> 原文:[https://www . geesforgeks . org/python-元素产品-使用-索引-列表/](https://www.geeksforgeeks.org/python-product-of-elements-using-index-list/)

在 python 中，从元素的索引中访问元素是一项更简单的任务，只需在列表中使用[]运算符就可以了。但是在某些情况下，当我们有不止一个索引时，我们会面临任务，我们需要获取与这些索引相对应的所有元素，然后执行乘法。让我们讨论完成这项任务的某些方法。

**方法#1:使用列表理解+循环**
这个任务很容易通过循环来执行，因此简写为第一个从这个任务开始的方法。迭代索引列表以从列表中获取相应的元素到新列表中是执行这个任务的强力方法。使用循环执行产品任务。

```
# Python3 code to demonstrate 
# Product of Index values
# using list comprehension + loop 

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# initializing lists 
test_list = [9, 4, 5, 8, 10, 14] 
index_list = [1, 3, 4] 

# printing original lists 
print ("Original list : " + str(test_list)) 
print ("Original index list : " + str(index_list)) 

# using list comprehension + loop to 
# Product of Index values 
res_list = prod([test_list[i] for i in index_list]) 

# printing result 
print ("Resultant list : " + str(res_list)) 
```

**Output :**

```
Original list : [9, 4, 5, 8, 10, 14]
Original index list : [1, 3, 4]
Resultant list : 320

```