# Python–列表中的后缀产品

> 原文:[https://www . geesforgeks . org/python-后缀-列表中的产品/](https://www.geeksforgeeks.org/python-suffix-product-in-list/)

如今，特别是在竞争编程领域，计算后缀产品的效用在许多问题上相当流行和有特色。因此，有一个单一的解决方案会有很大的帮助。让我们讨论一下解决这个问题的某些方法。

**方法:使用列表理解+循环+列表切片**
这个问题可以通过以上两个函数的组合来解决，其中我们使用列表理解来将逻辑扩展到每个元素，使用显式乘积函数来获得乘积，使用切片来获得乘积直到特定的索引。

```py
# Python3 code to demonstrate 
# Suffix List Product 
# using list comprehension + loop + list slicing 

# compute prod 
def prod(test_list): 
    res = 1
    for ele in test_list: 
        res = res * ele 
    return res 

# initializing list 
test_list = [3, 4, 1, 7, 9, 1] 

# printing original list 
print("The original list : " + str(test_list)) 

# using list comprehension + loop + list slicing 
# Suffix List Product
test_list.reverse() 
res = [prod(test_list[ : i + 1 ]) for i in range(len(test_list))] 

# print result 
print("The suffix product list is : " + str(res)) 
```

**Output :**

```py
The original list : [3, 4, 1, 7, 9, 1]
The suffix product list is : [1, 9, 63, 63, 252, 756]

```