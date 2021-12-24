# 查看 Python 中所有定义的变量

> 原文:[https://www . geesforgeks . org/view-所有定义的变量-在 python 中/](https://www.geeksforgeeks.org/viewing-all-defined-variables-in-python/)

在本文中，我们将讨论如何在 Python 中查看所有定义的变量。调试代码时，查看所有定义的变量起着重要作用。

**方法一:使用 dir()函数**

**dir()** 是一个内置函数，用来存储程序内部的所有变量以及内置的变量函数和方法。它创建所有声明的和内置的变量的列表。有两种不同的方法可以使用 dir()查看所有已定义的变量。它们将在下面讨论。

**当没有用户定义的变量以“__”开头时:**

*   定义一些不以“__”开头的各种类型的变量
*   调用 dir 并将其存储在变量中。它以列表的形式存储之前定义的所有变量名，并将变量名存储为字符串。
*   遍历存储 dir()的整个列表。
*   如果项目不以“__”开头，则打印该项目

**示例:**

## 蟒蛇 3

```
# Define some variables of various types
# that are not starting with '__'
var2 = "Welcome to geeksforgeeks"
var3 = {"1": "a", "2": "b"}
var4 = 25
var5 = [1, 2, 3, 4, 5]
var6 = (58, 59)

# call dir and store it in a variable.
# It stores all the variable names defined
# before in the form of a list
# and stores the variable names as a string.
all_variables = dir()

# Iterate over the whole list where dir( )
# is stored.
for name in all_variables:

    # Print the item if it doesn't start with '__'
    if not name.startswith('__'):
        myvalue = eval(name)
        print(name, "is", type(myvalue), "and is equal to ", myvalue)
```

**输出:**

> var2 是<class>并且等于欢迎来到极客论坛</class>
> 
> var3 为<class>，等于{'1': 'a '，' 2': 'b'}</class>
> 
> var4 为<class>，等于 25</class>
> 
> var5 是<class>并且等于[1，2，3，4，5]</class>
> 
> var6 为<class>且等于(58，59)</class>

**存储内置变量并忽略它们**

*   创建一个新变量，并使用 dir()在其中存储所有内置函数。
*   定义一些不同类型的变量。
*   再次调用 dir 并将其存储在一个列表中，减去先前存储的内置变量。
*   遍历整个列表。
*   打印所需的项目

**示例:**

## 蟒蛇 3

```
# Create a new variable and store all
# built-in functions within it using dir( ).
not_my_data = set(dir())

# Define some variables of various types.
var2 = "Welcome to geeksforgeeks"
var3 = {"1": "a", "2": "b"}
var4 = 25
var5 = [1, 2, 3, 4, 5]
var6 = (58, 59)

# Again call dir and store it in a list 
# subtracting the built-in variables stored
# previously.
my_data = set(dir()) - not_my_data

# Iterate over the whole list is stored.
for name in my_data:

    # Exclude the un-necessary variable named not_my_data
    if name != "not_my_data":
        val = eval(name)
        print(name, "is", type(val), "and is equal to ", val)
```

**输出:**

> var2 是<class>并且等于欢迎来到极客论坛</class>
> 
> var3 为<class>，等于{'1': 'a '，' 2': 'b'}</class>
> 
> var6 为<class>且等于(58，59)</class>
> 
> var4 为<class>，等于 25</class>
> 
> var5 是<class>并且等于[1，2，3，4，5]</class>

**方法二:打印局部和全局变量**

Locals()是一个内置函数，它返回该特定范围内所有局部变量的列表。而 globals()对全局变量也是如此。

**接近**

*   使用 globals()函数创建所有全局变量的列表，以存储内置的全局变量。
*   声明一些全局变量
*   声明一个函数。
*   在里面声明一些局部变量。
*   使用 locals 关键字将所有局部变量存储在列表中。
*   遍历列表并打印局部变量。
*   使用 globals 关键字将全局变量存储在列表中，并从中减去先前创建的内置全局变量列表。
*   打印出来。
*   调用函数。

**示例:**

## 蟒蛇 3

```
# Create a list of all global variables using
# globals( ) function, To store the built-in
# global variables.
not_my_data = set(globals())

# Declare some global variables
foo5 = "hii"
foo6 = 7

# Declare a function.
def func():

    # Declare some local variables inside it.
    var2 = "Welcome to geeksforgeeks"
    var3 = {"1": "a", "2": "b"}
    var4 = 25
    var5 = [1, 2, 3, 4, 5]
    var6 = (58, 59)

    # Store all the local variables in a list,
    # using locals keyword.
    locals_stored = set(locals())

    # Iterate over the list and print the local
    # variables.
    print("Printing Local Variables")
    for name in locals_stored:
        val = eval(name)
        print(name, "is", type(val), "and is equal to ", val)

    # Store the global variables in a list using 
    # globals keyword and subtract the previously
    # created list of built-in global variables from it.
    globals_stored = set(globals())-not_my_data

    # Print the global variables
    print("\nPrinting Global Variables")
    for name in globals_stored:

        # Excluding func and not_my_data as they are 
        # also considered as a global variable
        if name != "not_my_data" and name != "func":
            val = eval(name)
            print(name, "is", type(val), "and is equal to ", val)

# Call the function.
func()
```

**输出:**

> 打印局部变量
> 
> var2 是<class>并且等于欢迎来到极客论坛</class>
> 
> var6 为<class>且等于(58，59)</class>
> 
> var4 为<class>，等于 25</class>
> 
> var5 是<class>并且等于[1，2，3，4，5]</class>
> 
> var3 为<class>，等于{'1': 'a '，' 2': 'b'}</class>
> 
> 打印全局变量
> 
> foo6 是<class>，等于 7</class>
> 
> foo5 是<class>，等于 hii</class>