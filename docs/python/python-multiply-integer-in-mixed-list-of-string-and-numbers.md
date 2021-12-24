# Python |将字符串和数字混合列表中的整数相乘

> 原文:[https://www . geesforgeks . org/python-字符串和数字混合整数乘法列表/](https://www.geeksforgeeks.org/python-multiply-integer-in-mixed-list-of-string-and-numbers/)

有时候，在使用 Python 时，我们会遇到一个问题，我们需要找到列表的产品。这个问题比较容易解决。但是如果我们有混合的数据类型，这可能会变得复杂。让我们讨论执行这项任务的某些方法。

**方法#1:使用类型铸造+异常处理**
我们可以使用蛮力方法来键入种姓每个元素，并在出现异常时捕捉异常。这可以确保只有整数乘以乘积，因此可以解决这个问题。

```py
# Python3 code to demonstrate working of
# Mixed List Integer Multiplication
# using type caste and exception handling

# initializing list
test_list = [5, 8, "gfg", 8, (5, 7), 'is', 2]

# printing original list
print("The original list is : " + str(test_list))

# Mixed List Integer Multiplication
# using type caste and exception handling
res = 1
for ele in test_list:
    try:
        res *= int(ele)
    except :
        pass

# printing result 
print("Product of integers in list : " + str(res))
```

**Output :**

```py
The original list is : [5, 8, 'gfg', 8, (5, 7), 'is', 2]
Product of integers in list : 640

```