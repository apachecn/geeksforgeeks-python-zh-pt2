# Python |列表理解 vs *运算符

> 原文:[https://www . geesforgeks . org/python-list-understance-vs-operator/](https://www.geeksforgeeks.org/python-list-comprehension-vs-operator/)

* python 3 . x 中的运算符和 range()有很多用途。其中之一就是初始化列表。

**代码:初始化 1D-Python 列表**

```py
# Python code to initialize 1D-list  

# Initialize using star operator
# list of size 5 will be initialized.
# star is used outside the list.
list1 = [0]*5  

# Initialize using list comprehension
# list of size 5 will be initialized.
# range() is used inside list.
list2 = [0 for i in range(5)]  

print("list1 : ", list1)
print("list2 : ", list2)
```

**输出:**

```py
list1 :  [0, 0, 0, 0, 0]
list2 :  [0, 0, 0, 0, 0]

```