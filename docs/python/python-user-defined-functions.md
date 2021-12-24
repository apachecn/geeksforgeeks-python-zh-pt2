# Python 用户定义函数

> 原文:[https://www . geesforgeks . org/python-用户定义-函数/](https://www.geeksforgeeks.org/python-user-defined-functions/)

函数是一组接受输入、进行特定计算并产生输出的语句。其思想是将一些通常或重复完成的任务放在一起，并创建一个函数，这样我们就可以调用该函数，而不是针对不同的输入反复编写相同的代码。
Python 自带的函数称为内置函数。Python 提供了像 print()等内置函数。但是我们也可以创建您自己的函数。这些功能被称为**用户定义功能**。

> 目录
> 
> *   [用户自定义功能](#user-defined-functions)
>     
> *   [参数化函数](#parameterized-function)
>     *   [默认参数](#default-arguments)
>         
>     *   [关键词论点](#keyword-arguments)
>         
>     *   [可变长度参数](#variable-length-arguments)
>         
>     *   [按引用传递还是按值传递？](#pass-by-reference)
>         
> *   [带返回值的函数](#return)

## 用户定义的函数

任何用户编写的所有函数都属于用户定义函数的范畴。下面是用 Python 编写用户定义函数的步骤。

*   在 Python 中，def 关键字用于声明用户定义的函数。

*   包含函数主体的函数名和参数后面是缩进的语句块。

**语法:**

```py
def function_name():
    statements
    .
    .
```

**例:**

## 蟒蛇 3

```py
# Python program to
# demonstrate functions

# Declaring a function
def fun():
    print("Inside function")

# Driver's code
# Calling function
fun()
```

**输出:**

```py
Inside function
```

## 参数化函数

该函数可以将参数(也称为参数)作为左圆括号和右圆括号内的输入，就在函数名后面跟一个冒号。
**语法:**

```py
def function_name(argument1, argument2, ...):
    statements
    .
    .
```

**例:**

## 蟒蛇 3

```py
# Python program to
# demonstrate functions

# A simple Python function to check
# whether x is even or odd
def evenOdd( x ):
    if (x % 2 == 0):
        print("even")
    else:
        print("odd")

# Driver code
evenOdd(2)
evenOdd(3)
```

**输出:**

```py
even
odd
```

#### 默认参数

默认参数是一个参数，如果函数调用中没有为该参数提供值，则该参数采用默认值。以下示例说明了默认参数。
**例:**

## 蟒蛇 3

```py
# Python program to demonstrate
# default arguments
def myFun(x, y = 50):
    print("x: ", x)
    print("y: ", y)

# Driver code (We call myFun() with only
# argument)
myFun(10)
```

**输出:**

```py
x:  10
y:  50
```

**注意:**想了解更多默认参数[点击这里](https://www.geeksforgeeks.org/default-arguments-in-python/)。

#### 关键字参数

其思想是允许调用者用值指定参数名，这样调用者就不需要记住参数的顺序。
**例:**

## 蟒蛇 3

```py
# Python program to demonstrate Keyword Arguments
def student(firstname, lastname): 
     print(firstname, lastname) 

# Keyword arguments                  
student(firstname ='Geeks', lastname ='Practice')    
student(lastname ='Practice', firstname ='Geeks')
```

**输出:**

```py
Geeks Practice
Geeks Practice
```

#### 可变长度参数

我们可以有普通的和关键字可变数量的参数。

*   Python 中函数定义中的特殊语法*args 用于向函数传递可变数量的参数。它用于传递非关键字、可变长度的参数列表。

*   python 中函数定义中的特殊语法**kwargs 用于传递关键字化的可变长度参数列表。我们用 kwargs 这个名字来表示双星。原因是因为双星允许我们传递关键字参数(以及任意数量的参数)。

**例:**

## 蟒蛇 3

```py
# Python program to illustrate  
# *args and **kwargs
def myFun1(*argv): 
    for arg in argv: 
        print (arg)

def myFun2(**kwargs): 
    for key, value in kwargs.items():
        print ("% s == % s" %(key, value))

# Driver code
print("Result of * args: ")
myFun1('Hello', 'Welcome', 'to', 'GeeksforGeeks')

print("\nResult of **kwargs")
myFun2(first ='Geeks', mid ='for', last ='Geeks') 
```

**输出:**

```py
Result of *args: 
Hello
Welcome
to
GeeksforGeeks

Result of **kwargs
mid == for
first == Geeks
last == Geeks
```

**注意:**想了解更多变长参数[点击这里](https://www.geeksforgeeks.org/args-kwargs-python/)。

#### 按引用传递还是按值传递？

需要注意的一点是，在 Python 中，每个变量名都是一个引用。当我们将一个变量传递给一个函数时，会创建一个对该对象的新引用。Python 中的参数传递和 Java 中的引用传递是一样的。为了证实这一点，在下面的例子中使用了 Python 的内置 id()函数。
**例:**

## 蟒蛇 3

```py
# Python program to
# verify pass by reference

def myFun(x):
    print("Value received:", x, "id:", id(x))

# Driver's code
x = 12
print("Value passed:", x, "id:", id(x))
myFun(x)
```

**Output**

```py
Value passed: 12 id: 11094656
Value received: 12 id: 11094656
```

**输出:**

```py
Value passed: 12 id: 10853984
Value received: 12 id: 10853984
```

如果上述变量的值在函数内部发生了变化，那么它将创建一个不同的变量作为不可变的数字。但是，如果在函数内部修改了可变列表对象，那么这些更改也会反映在函数外部。
**例:**

## 蟒蛇 3

```py
def myFun(x, arr):
    print("Inside function")

    # changing integer will
    # Also change the reference
    # to the variable
    x += 10
    print("Value received", x, "Id", id(x))

    # Modifying mutable objects
    # will also be reflected outside
    # the function
    arr[0] = 0
    print("List received", arr, "Id", id(arr))

# Driver's code
x = 10
arr = [1, 2, 3]

print("Before calling function")
print("Value passed", x, "Id", id(x))
print("Array passed", arr, "Id", id(arr))
print()

myFun(x, arr)

print("\nAfter calling function")
print("Value passed", x, "Id", id(x))
print("Array passed", arr, "Id", id(arr))
```

**输出:**

```py
Before calling function
Value passed 10 Id 10853920
Array passed [1, 2, 3] Id 139773681420488

Inside function
Value received 20 Id 10854240
List received [0, 2, 3] Id 139773681420488

After calling function
Value passed 10 Id 10853920
Array passed [0, 2, 3] Id 139773681420488
```

## 带返回值的函数

有时我们可能需要函数的结果用于进一步的处理。因此，函数在完成执行时也应该返回值。这可以通过 return 语句实现。
return 语句用于结束函数调用的执行，并将结果(return 关键字后面的表达式的值)返回给调用者。返回语句之后的语句不会被执行。如果 return 语句没有任何表达式，则返回特殊值 None。
**语法:**

```py
def fun():
    statements
    .
    .
    return [expression]
```

**例:**

## 蟒蛇 3

```py
# Python program to
# demonstrate return statement

def add(a, b):

    # returning sum of a and b
    return a + b

def is_true(a):

    # returning boolean of a
    return bool(a)

# calling function
res = add(2, 3)
print("Result of add function is {}".format(res))

res = is_true(2<5)
print("\nResult of is_true function is {}".format(res))
```

**输出:**

```py
Result of add function is 5

Result of is_true function is True
```