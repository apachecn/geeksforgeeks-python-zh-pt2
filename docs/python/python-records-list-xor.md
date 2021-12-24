# Python |记录列表 XOR

> 原文:[https://www.geeksforgeeks.org/python-records-list-xor/](https://www.geeksforgeeks.org/python-records-list-xor/)

有时，在编程时，我们会遇到一个问题，即我们可能需要在元组列表元素之间执行某些按位操作。这是一个必不可少的工具，因为我们会多次遇到按位运算。让我们讨论一下执行异或运算的某些方法。

**方法#1:使用`reduce() + lambda + “^” operator` +循环**
以上功能可以组合执行此任务。我们可以首先使用循环展平元组列表，然后使用 reduce()来累加 lambda 函数指定的异或逻辑的结果。仅适用于 Python2。

```py
# Python code to demonstrate working of 
# Records list XOR
# Using reduce() + lambda + "^" operator + loops

# initializing list 
test_list = [(4, 6), (2, ), (3, 8, 9)] 

# printing original list 
print("The original list is : " + str(test_list)) 

# Records list XOR
# Using reduce() + lambda + "^" operator + loops
temp = []
for sub in test_list:
  for ele in sub:
    temp.append(ele)
res = reduce(lambda x, y: x ^ y, temp) 

# printing result 
print("The Bitwise XOR of records list elements are : " + str(res)) 
```

**Output :**

```py
The original list is : [(4, 6), (2, ), (3, 8, 9)]
The Bitwise XOR of records list elements are : 2

```