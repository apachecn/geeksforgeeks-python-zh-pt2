# 从函数返回函数–Python

> 原文:[https://www . geeksforgeeks . org/从函数返回函数-python/](https://www.geeksforgeeks.org/returning-a-function-from-a-function-python/)

[Python 中的函数](https://www.geeksforgeeks.org/functions-in-python/)是[一级对象](https://www.geeksforgeeks.org/first-class-functions-python/)。一种语言中的第一类对象在整个过程中被统一处理。它们可以存储在数据结构中，作为参数传递，或者用在控制结构中。

**一级函数的性质:**

*   函数是对象类型的一个实例。
*   您可以将函数存储在变量中。
*   您可以将函数作为参数传递给另一个函数。
*   您可以从函数返回函数。
*   您可以将它们存储在数据结构中，如哈希表、列表等

**示例 1:无参数函数**

在本例中，第一种方法是 A()，第二种方法是 B()。()方法返回 B()方法，该方法保留为名为 returned_function 的对象，并将用于调用第二个方法。

## 蟒蛇 3

```py
# define two methods

# second method that will be returned
# by first method
def B():
    print("Inside the method B.")

# first method that return second method
def A():
    print("Inside the method A.")

    # return second method
    return B

# form a object of first method
# i.e; second method
returned_function = A()

# call second method by first method
returned_function()
```

**输出:**

```py
Inside the method A.
Inside the method B.
```

**示例 2:带参数的函数**

在本例中，第一种方法是 A()，第二种方法是 B()。这里调用了一个()方法，该方法返回 B()方法，即；执行这两个功能。

## 蟒蛇 3

```py
# define two methods

# second method that will be returned
# by first method
def B(st2):
    print("Good " + st2 + ".")

# first method that return second method
def A(st1, st2):
    print(st1 + " and ", end = "")

    # return second method
    return B(st2)

# call first method that do two work:
# 1\. execute the body of first method, and
# 2\. execute the body of second method as
#    first method return the second method
A("Hello", "Morning")
```

**输出:**

```py
Hello and Good Morning.
```

**例 3:带λ的函数**

在这个例子中，第一个方法是 A()，第二个方法是未命名的，即；带着λ。()方法返回 lambda 语句方法，该方法作为名为 returned_function 的对象保存，并将用于调用第二个方法。

## 蟒蛇 3

```py
# first method that return second method
def A(u, v):
    w = u + v
    z = u - v

    # return second method without name
    return lambda: print(w * z)

# form a object of first method
# i.e; second method
returned_function = A(5, 2)

# check object
print(returned_function)

# call second method by first method
returned_function()
```

**输出:**

```py
<function A.<locals>.<lambda> at 0x7f65d8e17158>
21
```