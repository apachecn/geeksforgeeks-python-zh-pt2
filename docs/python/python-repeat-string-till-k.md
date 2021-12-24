# Python |重复字符串直到 K

> 原文:[https://www.geeksforgeeks.org/python-repeat-string-till-k/](https://www.geeksforgeeks.org/python-repeat-string-till-k/)

有时，在处理字符串时，我们可能会遇到一个用例，在这个用例中，我们需要将字符串重复到 K 的大小，即使最后一个字符串可能不完整，但是随着字符串的大小变成 K，必须停止。重复字符串 K 次的问题，相对来说比这个问题更简单。让我们讨论一下解决这个问题的方法。

**方法#1:使用列表切片和`// operator`**

可以使用上述工具执行此任务。在这种情况下，我们只是将字符串相乘，直到它变得大于或等于 K，然后使用列表切片方法省略额外字符串的切片。

```py
# Python3 code to demonstrate
# Repeat string till K
# using list slicing and // operator

# initializing string 
test_string = "GeeksforGeeks"

# initializing K 
K = 30

# printing original string 
print("The original string : " + str(test_string))

# using list slicing and // operator
# Repeat string till K
res = (test_string * (K//len(test_string)+ 1))[:K]

# print result
print("String after performing repeatition : " + res)
```

**Output :**

```py
The original string : GeeksforGeeks
String after performing repeatition : GeeksforGeeksGeeksforGeeksGeek

```

**方法 2:使用`divmod()` +列表切片**

上述方法中应用的除法可以在该方法中用`divmod` 函数代替，这以 40%的性能下降为代价提高了代码的可读性。

```py
# Python3 code to demonstrate
# Repeat string till K
# using divmod() + list slicing

# initializing string 
test_string = "GeeksforGeeks"

# initializing K 
K = 30

# printing original string 
print("The original string : " + str(test_string))

# using divmod() + list slicing
# Repeat string till K
div, mod = divmod(K, len(test_string))
res = test_string * div + test_string[:mod]

# print result
print("String after performing repeatition : " + res)
```

**Output :**

```py
The original string : GeeksforGeeks
String after performing repeatition : GeeksforGeeksGeeksforGeeksGeek

```