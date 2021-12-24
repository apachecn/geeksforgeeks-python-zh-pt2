# Python |同值空间和异值空间

> 原文:[https://www . geesforgeks . org/python-同值异值空间/](https://www.geeksforgeeks.org/python-same-and-different-value-space/)

在 Python 中，我们有相同的池来存储相似的值，即使它们共享不同的变量。这有很多优点，为相似的值安排不同的空间可以节省大量的内存。这是为小整数提供的。但是有一些方法可以让我们拥有相同和不同的池值。让我们讨论相同的某些情况。

**案例#1:同一个池(使用+运算符)**
在本例中，当我们使用“+”运算符创建一个 String 时，我们会创建一个指向内存中类似空间的空间。

```
# Python3 code to demonstrate working of 
# Same and Different value space
# Same value case

# initializing strings
test_str1 = "gfg"

# printing original string
print("The original string is : " + test_str1)

# Using + to construct second string 
test_str2 = "g" + "fg"

# testing values 
res = test_str1 is test_str2

# printing result 
print("Are values pointing to same pool ? : " + str(res)) 
```

**Output :**

```
The original string is : gfg
Are values pointing to same pool ? : True

```