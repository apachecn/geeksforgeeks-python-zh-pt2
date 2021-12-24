# Python 中的 str() vs repr()

> 原文:[https://www.geeksforgeeks.org/str-vs-repr-in-python/](https://www.geeksforgeeks.org/str-vs-repr-in-python/)

str()和 repr()都用于获取对象的字符串表示形式。

1.  **Example of str():**

    ```
    s = 'Hello, Geeks.'
    print (str(s))
    print (str(2.0/11.0))
    ```

    输出:

    ```
    Hello, Geeks.
    0.181818181818
    ```

    。

2.  **Example of repr():**

    ```
    s = 'Hello, Geeks.'
    print (repr(s))
    print (repr(2.0/11.0))
    ```

    输出:

    ```
    'Hello, Geeks.'
    0.18181818181818182
    ```

从上面的输出中，我们可以看到，如果我们使用 repr()函数打印字符串，那么它会打印一对引号，如果我们计算一个值，我们会得到比 str()函数更精确的值。

以下是不同之处:

*   ***str()用于为最终用户创建输出，而 repr()主要用于调试和开发。repr 的目标是明确的，str 的目标是可读的*** 。例如，如果我们怀疑一个浮点数有一个小的舍入误差，repr 将显示给我们，而 str 可能没有。
*   repr() [计算对象的“正式”字符串表示形式](http://docs.python.org/reference/datamodel.html#object.__repr__)(一种包含对象所有信息的表示形式)，str()用于[计算对象的“非正式”字符串表示形式](http://docs.python.org/reference/datamodel.html#object.__str__)(一种用于打印对象的表示形式)。
*   print 语句和 str()内置函数使用 __str__ 显示对象的字符串表示形式，而 repr()内置函数使用 __repr__ 显示对象。

让我们通过一个例子来理解这一点

```
import datetime
today = datetime.datetime.now()

# Prints readable format for date-time object
print (str(today))

# prints the official format of date-time object
print (repr(today))     
```

输出:

```
2016-02-22 19:32:04.078030
datetime.datetime(2016, 2, 22, 19, 32, 4, 78030)

```

str()以用户可以理解日期和时间的方式显示今天的日期。

repr()打印日期时间对象的“官方”表示(意味着使用“官方”字符串表示我们可以重建对象)。

**如何让它们为我们自己定义的类工作？**
如果我们需要调试的详细信息，一个用户定义的类也应该有一个 __repr__。如果我们认为为用户提供一个字符串版本是有用的，我们就创建一个 __str__ 函数。

```
# Python program to demonstrate writing of __repr__ and
# __str__ for user defined classes

# A user defined class to represent Complex numbers
class Complex:

    # Constructor
    def __init__(self, real, imag):
       self.real = real
       self.imag = imag

    # For call to repr(). Prints object's information
    def __repr__(self):
       return 'Rational(%s, %s)' % (self.real, self.imag)    

    # For call to str(). Prints readable form
    def __str__(self):
       return '%s + i%s' % (self.real, self.imag)    

# Driver program to test above
t = Complex(10, 20)

# Same as "print t"
print (str(t))  
print (repr(t))
```

输出:

```
10 + i20
Rational(10, 20)
```

本文由 **Arpit Agarwal 供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论