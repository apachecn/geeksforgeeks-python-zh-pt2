# Python 程序检查字符串是否为空

> 原文:[https://www . geesforgeks . org/python-程序检查字符串是否为空/](https://www.geeksforgeeks.org/python-program-to-check-if-string-is-empty-or-not/)

Python 字符串是不可变的，因此在谈论其操作时会有更复杂的处理。请注意，带有空格的字符串实际上是一个空字符串，但大小不为零。本文还讨论了这个问题及其解决方法。
我们来看看检查字符串是否为空的不同方法。
**方法#1:使用 len()**
使用 len()是检查零长度字符串最通用的方法。即使它忽略了这样一个事实，即一个只有空格的字符串实际上也应该被认为是空字符串，即使它不是零。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to check if string is empty
# using len()

# initializing string
test_str1 = ""
test_str2 = "  "

# checking if string is empty
print ("The zero length string without spaces is empty ? : ", end = "")
if(len(test_str1) == 0):
    print ("Yes")
else :
    print ("No")

# prints No
print ("The zero length string with just spaces is empty ? : ", end = "")
if(len(test_str2) == 0):
    print ("Yes")
else :
    print ("No")
```

**输出:**

```
The zero length string without spaces is empty ? : Yes
The zero length string with just spaces is empty ? : No
```

**方法 2:使用 not**
not 运算符也可以执行类似 len()的任务，并检查 0 长度字符串，但与上面相同，它认为只有空格的字符串也是非空的，这实际上不应该是真的。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to check if string is empty
# using not

# initializing string
test_str1 = ""
test_str2 = "  "

# checking if string is empty
print ("The zero length string without spaces is empty ? : ", end = "")
if(not test_str1):
    print ("Yes")
else :
    print ("No")

# prints No
print ("The zero length string with just spaces is empty ? : ", end = "")
if(not test_str2):
    print ("Yes")
else :
    print ("No")
```

**输出:**

```
The zero length string without spaces is empty ? : Yes
The zero length string with just spaces is empty ? : No
```

**方法三:使用 not + str.strip()**
空+零长度字符串的问题可以通过使用 strip()来解决，strip()如果遇到空格会返回 true，因此检查它可以解决检查纯空字符串的问题。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to check if string is empty
# using not + strip()

# initializing string
test_str1 = ""
test_str2 = "  "

# checking if string is empty
print ("The zero length string without spaces is empty ? : ", end = "")
if(not (test_str1 and test_str1.strip())):
    print ("Yes")
else :
    print ("No")

# prints Yes
print ("The zero length string with just spaces is empty ? : ", end = "")
if(not(test_str2 and test_str2.strip())):
    print ("Yes")
else :
    print ("No")
```

**输出:**

```
The zero length string without spaces is empty ? : Yes
The zero length string with just spaces is empty ? : Yes
```

**方法#4:使用 not + str.isspace**
的工作方式与上述方法类似，并检查字符串中的空格。这种方法效率更高，因为如果空间数量足够多，strip()需要执行同样需要计算负荷的 strip 操作。

## 蟒蛇 3

```
# Python 3 code to demonstrate
# to check if string is empty
# using not + isspace()

# initializing string
test_str1 = ""
test_str2 = "  "

# checking if string is empty
print ("The zero length string without spaces is empty ? : ", end = "")
if(not (test_str1 and not test_str1.isspace())):
    print ("Yes")
else :
    print ("No")

# prints Yes
print ("The zero length string with just spaces is empty ? : ", end = "")
if(not (test_str2 and not test_str2.isspace())):
    print ("Yes")
else :
    print ("No")
```

**输出:**

```
The zero length string without spaces is empty ? : Yes
The zero length string with just spaces is empty ? : Yes
```