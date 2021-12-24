# Python |方法重载

> 原文:[https://www.geeksforgeeks.org/python-method-overloading/](https://www.geeksforgeeks.org/python-method-overloading/)

像其他语言(例如 C++中的[方法重载](https://www.geeksforgeeks.org/function-overloading-c/))一样，python 默认不支持方法重载。但是在 Python 中有不同的方法来实现方法重载。

Python 中方法重载的问题是，我们可能会重载方法，但只能使用最新定义的方法。

## 蟒蛇 3

```
# First product method.
# Takes two argument and print their
# product
def product(a, b):
    p = a * b
    print(p)

# Second product method
# Takes three argument and print their
# product
def product(a, b, c):
    p = a * b*c
    print(p)

# Uncommenting the below line shows an error    
# product(4, 5)

# This line will call the second product method
product(4, 5, 5)
```

**输出:**

```
100
```

在上面的代码中，我们定义了两个产品方法，但是我们只能使用第二个产品方法，因为 python 不支持方法重载。我们可以定义许多同名不同参数的方法，但只能使用最新定义的方法。调用另一个方法会产生错误。就像这里调用![product(4, 5)    ](img/dd54ec4b865e84cd07018e176dd7dd4e.png "Rendered by QuickLaTeX.com")会产生一个错误，因为最新定义的乘积方法需要三个参数。

因此，为了克服上述问题，我们可以使用不同的方法来实现方法重载。

**方法 1(不是最有效的方法):**
我们可以使用参数使同一个函数以不同的方式工作，即根据参数工作。

## 蟒蛇 3

```
# Function to take multiple arguments
def add(datatype, *args):

    # if datatype is int
    # initialize answer as 0
    if datatype =='int':
        answer = 0

    # if datatype is str
    # initialize answer as ''
    if datatype =='str':
        answer =''

    # Traverse through the arguments
    for x in args:

        # This will do addition if the 
        # arguments are int. Or concatenation 
        # if the arguments are str
        answer = answer + x

    print(answer)

# Integer
add('int', 5, 6)

# String
add('str', 'Hi ', 'Geeks')
```

**输出:**

```
11
Hi Geeks
```

上述代码的问题在于，使用多个 if/else 语句会使代码变得更加复杂，并且这不是实现方法重载的理想方式。

**方法 2(高效的):**
通过使用多重调度装饰器
多重调度装饰器可以通过以下方式安装:

```
pip3 install multipledispatch
```

## 蟒蛇 3

```
from multipledispatch import dispatch

#passing one parameter
@dispatch(int,int)
def product(first,second):
    result = first*second
    print(result);

#passing two parameters
@dispatch(int,int,int)
def product(first,second,third):
    result  = first * second * third
    print(result);

#you can also pass data type of any value as per requirement
@dispatch(float,float,float)
def product(first,second,third):
    result  = first * second * third
    print(result);

#calling product method with 2 arguments
product(2,3,2) #this will give output of 12
product(2.2,3.4,2.3) # this will give output of 17.985999999999997
```

**输出:**

```
12
17.985999999999997
```

在后端，Dispatcher 创建一个存储不同实现的对象，在运行时，它选择适当的方法作为传递参数的类型和数量。