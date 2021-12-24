# Python–选择性元组键的乘积

> 原文:[https://www . geeksforgeeks . org/python-选择性元组密钥产品/](https://www.geeksforgeeks.org/python-product-of-selective-tuple-keys/)

有时，在使用元组列表时，我们会遇到这样一个问题，即我们有某个键列表，而我们只需要元组列表中这些键的值的乘积。这在特定实体的评级或产品中具有效用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`dict() + loop + get()` +列表理解**
我们可以执行这个特定的任务，首先将列表转换成字典，然后使用列表理解使用 get 函数获取特定键的值。值的乘积使用循环执行。

```
# Python3 code to demonstrate 
# Product of Selective Tuple Keys
# using dict() + get() + list comprehension + loop

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# initializing list of tuples 
test_list = [('Nikhil', 1), ('Akash', 2), ('Akshat', 3), ('Manjeet', 4)]

# initializing selection list 
select_list = ['Nikhil', 'Akshat']

# printing original list 
print ("The original list is : " + str(test_list))

# printing selection list 
print ("The selection list is : " + str(select_list))

# using dict() + get() + list comprehension + loop
# Product of Selective Tuple Keys
temp = dict(test_list)
res = prod([temp.get(i, 0) for i in select_list])

# printing result
print ("The selective values product of keys : " + str(res))
```

**Output :**

```
The original list is : [('Nikhil', 1), ('Akash', 2), ('Akshat', 3), ('Manjeet', 4)]
The selection list is : ['Nikhil', 'Akshat']
The selective values product of keys : 3

```