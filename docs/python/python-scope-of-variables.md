# Python 变量范围

> 原文:[https://www.geeksforgeeks.org/python-scope-of-variables/](https://www.geeksforgeeks.org/python-scope-of-variables/)

在 Python 中，变量是存储数据值的容器。它们是内存中对象的引用或指针，这意味着每当一个变量被分配给一个实例时，它就被映射到该实例。与 C/C++/JAVA 等其他语言不同，Python 不是“静态类型的”。我们不需要在使用变量之前声明变量或者声明它们的类型。当我们第一次给变量赋值时，它就被创建了。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# variable assignment

# An integer assignment
age = 45                     

# A floating point
salary = 1456.8            

# A string  
name = "John"             

print(age)
print(salary)
print(name)
```

**输出:**

```
45
1456.8
John
```

**注意:**想了解更多变量[点击这里](https://www.geeksforgeeks.org/python-variables/)。

## 变量作用域

我们可以找到一个变量并在需要时访问它的位置被称为变量的**范围。** 

#### 全局和局部变量

全局变量是在任何函数之外定义和声明的变量，并且没有指定给任何函数。它们可以被程序的任何部分使用。
**例:**

## 蟒蛇 3

```
# This function uses global variable s
def f(): 
    print(s)

# Global scope
s = "I love Geeksforgeeks"
f()
```

**输出:**

```
I love Geeksforgeeks
```

现在假设在函数的作用域内定义了一个同名的变量，那么它将只打印函数内部给出的值，而不是全局值。

## 蟒蛇 3

```
# This function has a variable with
# name same as s.
def f(): 
    s = "Me too."
    print(s)

# Global scope
s = "I love Geeksforgeeks"
f()
print(s)
```

**输出:**

```
Me too.
I love Geeksforgeeks
```

在我们调用函数 f()之前，变量 s 被定义为字符串“我爱极客”。f()中唯一的语句是 print 语句。由于没有本地 s，将使用全局 s 的值。
问题是，如果我们改变函数 f()内部 s 的值会发生什么？它也会影响全球吗？我们在下面的代码中测试它:

## 蟒蛇 3

```
def f(): 
    print(s)

    # This program will NOT show error
    # if we comment below line. 
    s = "Me too."

    print(s)

# Global scope
s = "I love Geeksforgeeks"
f()
print(s)
```

**输出:**

```
Traceback (most recent call last):
  File "/home/370cac45bae7f1e6096520b7a0edb604.py", line 13, in 
    f() 
  File "/home/370cac45bae7f1e6096520b7a0edb604.py", line 3, in f
    print(s) 
UnboundLocalError: local variable 's' referenced before assignment
```

要让上述程序工作，我们需要使用**全局**关键字。我们只需要在函数中使用全局关键字，如果我们想做赋值/改变它们的话。打印和访问不需要全局。为什么呢？Python“假设”我们想要一个局部变量，因为在 f()内部赋值给了 s，所以第一个 print 语句抛出了这个错误消息。任何在函数内部更改或创建的变量都是局部变量，如果它没有被声明为全局变量的话。要告诉 Python，我们想要使用全局变量，我们必须使用关键字 global，如下例所示:

## 蟒蛇 3

```
# This function modifies global variable 's'
def f():
    global s
    print(s)
    s = "Look for Geeksforgeeks Python Section"
    print(s)

# Global Scope
s = "Python is great !"
f()
print(s)
```

**输出:**

```
Python is great!
Look for Geeksforgeeks Python Section
Look for Geeksforgeeks Python Section
```

考虑下面的例子，以便更好地理解这个主题。

## 蟒蛇 3

```
# Python program to demonstrate
# scope of variable

a = 1

# Uses global because there is no local 'a'
def f():
    print('Inside f() : ', a)

# Variable 'a' is redefined as a local
def g():    
    a = 2
    print('Inside g() : ', a)

# Uses global keyword to modify global 'a'
def h():    
    global a
    a = 3
    print('Inside h() : ', a)

# Global scope
print('global : ', a)
f()
print('global : ', a)
g()
print('global : ', a)
h()
print('global : ', a)
```

**输出:**

```
global :  1
Inside f() :  1
global :  1
Inside g() :  2
global :  1
Inside h() :  3
global :  3
```

#### 非本地关键字

在 Python 中，非局部关键字用于嵌套函数的情况。这个关键字的工作方式类似于 global，但是在嵌套函数的情况下，这个关键字声明一个变量来指向外部封闭函数的变量，而不是 global。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# nonlocal keyword

print ("Value of a using nonlocal is : ", end ="")
def outer():
    a = 5
    def inner():
        nonlocal a 
        a = 10
    inner()
    print (a)

outer()

# demonstrating without non local 
# inner loop not changing the value of outer a
# prints 5
print ("Value of a without using nonlocal is : ", end ="")
def outer():
    a = 5
    def inner():
        a = 10
    inner()
    print (a)

outer()
```

**输出:**

```
Value of a using nonlocal is : 10
Value of a without using nonlocal is : 5
```