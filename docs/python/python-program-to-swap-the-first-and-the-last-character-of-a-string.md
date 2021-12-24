# Python 程序交换字符串的第一个和最后一个字符

> 原文:[https://www . geesforgeks . org/python-program-to-swap-字符串的第一个和最后一个字符/](https://www.geeksforgeeks.org/python-program-to-swap-the-first-and-the-last-character-of-a-string/)

给定一个字符串。任务是交换字符串的第一个和最后一个字符。

**例:**

```py
Input: GeeksForGeeks
Output: seeksForGeekG

Input: Python
Output: nythoP
```

Python 字符串是不可变的，这意味着我们不能直接修改它。但是 Python 有[字符串切片](https://www.geeksforgeeks.org/string-slicing-in-python/)，这使得执行字符串操作和进行修改变得非常容易。按照以下步骤交换字符–

1.  We initialize a variable **start, and** stores the first character of the string ( **string [0]** ).
2.  We initialize another variable **end** to store the last character ( **string [-1]** )
3.  Then we will use the string slice, **string [1:-1]** , which will access the division from the second position.
4.  Then we add these three as needed to form a new string, and the first and last characters of the string are exchanged with the original string. Then we will print it out.

下面是实现。

T2T4

```py
def swap(string):

    # storing the first character
    start = string[0]

    # storing the last character
    end = string[-1]

    swapped_string = end + string[1:-1] + start
    print(swapped_string)

# Driver Code
swap("GeeksforGeeks")
swap("Python")
```

T5

**输出:**

```py
seeksforGeekG
nythoP
```