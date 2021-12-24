# Python 程序输入逗号分隔的字符串

> 原文:[https://www . geesforgeks . org/python-程序到输入-逗号分隔字符串/](https://www.geeksforgeeks.org/python-program-to-input-a-comma-separated-string/)

给定一个逗号分隔而不是空格的输入字符串。任务是将这个输入字符串存储在一个列表或变量中。这可以通过两种方式在 Python 中实现:

*   **使用列表理解和`split()`T2】**
*   **使用`map()`和`split()`**

**方法 1:** 使用列表理解和`split()`

`[split()](https://www.geeksforgeeks.org/python-string-split/)`功能有助于从用户那里获得多种输入。它通过指定的分隔符中断给定的输入。如果没有提供分隔符，则任何空格都用作分隔符。一般来说，用户使用`split()`方法分割 Python 字符串，但也可以使用它进行多种输入。

**示例:**

```py
# Python program to take a comma
# separated string as input

# Taking input when the numbers 
# of input are known and storing
# in different variables

# Taking 2 inputs
a, b = [int(x) for x in input("Enter two values\n").split(', ')]
print("\nThe value of a is {} and b is {}".format(a, b))

# Taking 3 inputs
a, b, c = [int(x) for x in input("Enter three values\n").split(', ')]
print("\nThe value of a is {}, b is {} and c is {}".format(a, b, c))

# Taking multiple inputs
L = [int(x) for x in input("Enter multiple values\n").split(', ')]
print("\nThe values of input are", L) 
```

**输出:**

```py
Enter two values
1, 2

The value of a is 1 and b is 2
Enter three values
1, 2, 3

The value of a is 1, b is 2 and c is 3
Enter multiple values
1, 22, 34, 6, 88, 2

The values of input are [1, 22, 34, 6, 88, 2]

```

**方法二:**使用`map()`和`split()`

`[map()](https://www.geeksforgeeks.org/python-map-function/)`函数将给定的函数应用于给定可迭代表(列表、元组等)的每个项目后，返回结果列表。)

```py
# Python program to take a comma
# separated string as input

# Taking input when the numbers 
# of input are known and storing
# in different variables

# Taking 2 inputs
a, b = map(int, input("Enter two values\n").split(', '))
print("\nThe value of a is {} and b is {}".format(a, b))

# Taking 3 inputs
a, b, c = map(int, input("Enter three values\n").split(', '))
print("\nThe value of a is {}, b is {} and c is {}".format(a, b, c))

# Taking multiple inputs
L = list(map(int, input("Enter multiple values\n").split(', ')))
print("\nThe values of input are", L)
```

**输出:**

```py
Enter two values
1, 2

The value of a is 1 and b is 2
Enter three values
1, 2, 3

The value of a is 1, b is 2 and c is 3
Enter multiple values
1, 2, 3, 4

The values of input are [1, 2, 3, 4]

```