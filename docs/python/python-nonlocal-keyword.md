# Python 非本地关键字

> 原文:[https://www.geeksforgeeks.org/python-nonlocal-keyword/](https://www.geeksforgeeks.org/python-nonlocal-keyword/)

**Python 非局部关键字**用于使引用的变量在最近范围内有界。它绑定到的变量的作用域不应是全局或局部作用域。在 Python 中，非本地变量遵循与相同绑定不同的行为，它在另一个范围内搜索变量。嵌套函数中使用了非局部变量。非局部变量用于声明变量。

## **非本地的优势:**

*   它有助于访问不在同一范围内的变量。
*   因为它使一个变量引用另一个变量，所以它使该变量更加可重用，并为新变量节省内存。

## **非本地的劣势:**

*   非局部变量不与全局和局部变量一起使用。
*   非局部变量不用于不在嵌套范围内的变量。

### **演示非局部变量:**

**例 1:** 在本例中，我们演示了非局部变量的工作。我们创建非局部变量，并在嵌套范围内改变其内容，并影响上部范围内变量的内容。

## 蟒蛇 3

```
# Python code to demonstrait
# nonlocal keyword

# Nested function to demonstrait
# nonlocal keyword

def geek_func():

    # local variable to geek_func
    geek_name = "geek"
    # Inner function

    def geek_func2():

        # Declairing nonlocal variable
        nonlocal geek_name
        geek_name = 'GeekForGeeks'

        # Printing our variable
        print(geek_name)

    # Calling inner function
    geek_func2()

    # Printing local variable
    print(geek_name)

geek_func()
```

**输出:**

```
GeekForGeeks
GeekForGeeks   
```

**示例 2:** 在这个示例中，我们看到了当我们使一个非局部变量引用全局变量时会发生什么。

## 蟒蛇 3

```
# Python code to demonstrait
# nonlocal keyword

# Nested function to demonstrait
# nonlocal keyword

# Declairing variable in global scope
geek_name = 'geekforgeeks'

def geek_func():

    # Defining inner function
    def geek_func2():

        # Declairing nonlocal variable
        nonlocal geek_name
        geek_name = 'GeekForGeeks'

        # Printing our variable
        print(geek_name)

    # Calling inner function
    geek_func2()

geek_func()
```

**输出:**

```
SyntaxError: no binding for nonlocal 'geek_name' found
```

非局部变量的可能应用是，当访问另一个作用域的变量而不创建新变量时，它引用最近绑定到它的变量。非本地关键词有很多可能的应用。

**示例 3:** 在这个示例中，我们将看到当我们有多个嵌套函数并且它们都有一个同名的变量时，非局部引用了哪个变量。

## 蟒蛇 3

```
# Python code to demonstrait
# nonlocal keyword

# Nested function to demonstrait
# nonlocal keyword
def geek_func():

    # local variable to geek_func
    geek_name = "geekforgeeks"

    # First Inner function
    def geek_func1():
        geek_name = "GeekforGeeks"

        # Second Inner function
        def geek_func2():

             # Declairing nonlocal variable
            nonlocal geek_name
            geek_name = 'GEEKSFORGEEKS'

            # Printing our nonlocal variable
            print(geek_name)

       # Calling Second inner function
        geek_func2()

        # Calling First inner function
    geek_func1()

    # Printing local variable to geek_func
    print(geek_name)

geek_func()
```

**输出:**

```
GEEKSFORGEEKS
geekforgeeks
```