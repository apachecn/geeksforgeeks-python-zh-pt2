# 显示第一个字符串中的字母但不显示第二个字符串的 Python 程序

> 原文:[https://www . geesforgeks . org/python-显示第一个字符串中的字母但不是第二个的程序/](https://www.geeksforgeeks.org/python-program-that-displays-the-letters-that-are-in-the-first-string-but-not-in-the-second/)

Python 程序显示第一个字符串中的字母，但不显示第二个字符串中的字母，这可以通过取两组并减去它们来实现。由于集合支持差分运算符，一个集合可以包含第一个字符串的字母，另一个集合可以包含第二个字符串的字母，当减去后，我们可以获得所需的结果。

**例:**

```py
Input: set1 = { 'r', 'o', 'h', 'a', 'n'}
       set2 = { 'r', 'i', 't', 'i', 'k', 'a'}
Output: set1 - set2 = { 'o', 'h', 'n'}

Input: a = { 'g', 'e', 'e', 'k', 's', 'f', 'o', 'r'}
       b = { 'g', 'e', 'e', 'k', 's'}
Output: c = a - b = { 'f', 'o', 'r'}

```

**进场:**

*   拿两根绳子，比如说，a 和 b
*   将这些字符串转换成集合，比如说，setA 和 setB
*   从 setA 中减去 setB
*   打印结果

以下是上述方法的一些示例。

**例 1:**

## 蟒 3

```py
# string 1
a = "geeksforgeeks"

# string 2
b = "geeks"

# convert string 1 into set
setA = set(a)

# convert string 2 into set
setB = set(b)

# store the difference in form of list
result = setA-setB

# print result
print(result)
```

**输出**

```py
{'r', 'f', 'o'}

```

**例 2:**

## 蟒 3

```py
# string 1
a = "rohan"

# string 2
b = "mohali"

# store the difference of sets
result = set(a)-set(b)

# print result
print(result)
```

**输出**

```py
{'r', 'n'}

```

**注意:**以上程序的输出总是不同的，因为集合是无序的集合，因此减去它们会产生无序的结果。

通过上述方法，我们可以获得第一个字符串中的所有字母，但不能获得第二个字符串中的所有字母。