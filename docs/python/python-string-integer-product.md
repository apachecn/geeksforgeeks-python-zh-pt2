# Python–字符串整数积

> 原文:[https://www . geesforgeks . org/python-string-integer-product/](https://www.geeksforgeeks.org/python-string-integer-product/)

有时，在处理数据时，我们会遇到一个问题，即我们收到一系列字符串格式的数据列表，我们希望找到每个字符串列表整数的乘积。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `int()`**
这是执行这个任务的蛮力方法。在这种情况下，我们对整个列表运行一个循环，将每个字符串转换为整数，执行 product listwise 并存储在一个单独的列表中。

```
# Python3 code to demonstrate working of
# String Integer Product
# using loop + int()

# getting Product
def prod(val) :
    res = 1 
    for ele in val:
        res *= int(ele)
    return res 

# initialize list 
test_list = [['1', '4'], ['5', '6'], ['7', '10']]

# printing original list 
print("The original list : " + str(test_list))

# String Integer Product
# using loop + int()
res = []
for sub in test_list:
    par_prod = prod(sub)
    res.append(par_prod)

# printing result
print("List after product of nested string lists : " + str(res))
```

**Output :**

```
The original list : [['1', '4'], ['5', '6'], ['7', '10']]
List after product of nested string lists : [4, 30, 70]

```