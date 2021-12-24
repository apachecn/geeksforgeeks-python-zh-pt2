# Python 变量

> 原文:[https://www.geeksforgeeks.org/python-variables/](https://www.geeksforgeeks.org/python-variables/)

[Python](https://www.geeksforgeeks.org/python-programming-language/) 不是“静态类型化”。我们不需要在使用变量之前声明变量或者声明它们的类型。当我们第一次给变量赋值时，它就被创建了。变量是给一个内存位置起的名字。它是程序中的基本存储单元。

*   存储在变量中的值可以在程序执行过程中更改。
*   变量只是给一个内存位置起的名字，所有对变量的操作都会影响这个内存位置。

### **Python 中创建变量的规则:**

*   变量名必须以字母或下划线字符开头。
*   变量名不能以数字开头。
*   变量名只能包含字母数字字符和下划线(A-z、0-9 和 _)。
*   变量名区分大小写(名称、名字和名字是三个不同的变量)。
*   保留字(关键字)不能用于命名变量。

**我们来看看简单的变量创建:**

## 蟒蛇 3

```
#!/usr / bin / python

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

### **声明变量:**

让我们看看如何声明变量并打印变量。

## 蟒蛇 3

```
# declaring the var
Number = 100

# display
print( Number)
```

**输出:**

```
100

```

### **重新声明变量:**

一旦我们已经声明了 python 变量，我们就可以重新声明该变量。

## 蟒蛇 3

```
# declaring the var
Number = 100

# display
print("Before declare: ", Number)

# re-declare the var
Number = 120.3

print("After re-declare:", Number)
```

**输出:**

```
Before declare:  100
After re-declare: 120.3

```

### **给多个变量赋值:**

另外，Python 允许用“=”运算符同时给几个变量赋值。
例如:

## 蟒蛇 3

```
#!/usr / bin / python

a = b = c = 10

print(a)
print(b)
print(c)
```

**输出:**

```
10
10
10
```

### **给多个变量分配不同的值:**

Python 允许用“，”运算符在一行中添加不同的值。

## 蟒蛇 3

```
#!/usr / bin / python

a, b, c = 1, 20.2, "GeeksforGeeks"

print(a)
print(b)
print(c)
```

**输出:**

```
1
20.2
GeeksforGeeks
```

### **不同类型可以用****同一个名字吗？**

如果我们使用相同的名称，变量开始引用新的值和类型。

## 蟒蛇 3

```
#!/usr / bin / python

a = 10
a = "GeeksforGeeks"

print(a)
```

**输出:**

```
GeeksforGeeks
```

### **+运算符如何处理变量？**

## 蟒蛇 3

```
#!/usr / bin / python

a = 10
b = 20
print(a+b)

a = "Geeksfor"
b = "Geeks"
print(a+b)
```

**Output**

```
30
GeeksforGeeks

```

### **不同类型也可以用+吗？**

不同类型的使用不会产生错误。

## 蟒蛇 3

```
#!/usr / bin / python

a = 10
b = "Geeks"
print(a+b)
```

**输出:**

```
TypeError: unsupported operand type(s) for +: 'int' and 'str'

```

### Python 中的全局和局部变量:

**局部** **变量** 是在函数内部定义和声明的变量。我们不能在函数外调用这个变量。

## 蟒蛇 3

```
# This function uses global variable s
def f():
    s = "Welcome geeks"
    print(s)

f()
```

**输出:**

```
Welcome geeks

```

**全局变量**是在函数外部定义和声明的变量，我们需要在函数内部使用它们。

## 蟒蛇 3

```
# This function has a variable with
# name same as s.
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

### Python 中的全局关键字:

Global 关键字是允许用户修改当前范围之外的变量的关键字。它用于从非全局范围(即函数内部)创建 [全局变量](https://www.geeksforgeeks.org/global-local-variables-python/) 。Global 关键字仅在我们想要进行赋值或想要更改变量时才在函数中使用。打印和访问不需要全局。

**全局关键字规则:**

*   如果一个变量在函数体中的任何地方被赋值，除非显式声明为全局变量，否则它被认为是局部变量。
*   仅在函数内部引用的变量是隐式全局变量。
*   我们使用全局关键字在函数中使用全局变量。
*   不需要在函数外使用全局关键字。

**示例:**

## 蟒蛇 3

```
# Python program to modify a global
# value inside a function

x = 15

def change():

    # using a global keyword
    global x

    # increment value of a by 5
    x = x + 5
    print("Value of x inside a function :", x)

change()
print("Value of x outside a function :", x)
```

**输出:**

```
Value of x inside a function : 20
Value of x outside a function : 20

```

### Python 中的变量类型:

数据类型是数据项的分类或归类。它表示一种值，该值告诉可以对特定数据执行哪些操作。因为在 Python 编程中一切都是对象，所以数据类型实际上是类，变量是这些类的实例(对象)。

以下是 Python 的标准或内置数据类型:

*   数字的
*   序列类型
*   布尔代数学体系的
*   一组
*   词典

**示例:**

## 蟒蛇 3

```
# numberic
var = 123
print("Numbric data : ", var)

# Sequence Type
String1 = 'Welcome to the Geeks World'
print("String with the use of Single Quotes: ")
print(String1)

# Boolean
print(type(True))
print(type(False))

# Creating a Set with
# the use of a String
set1 = set("GeeksForGeeks")
print("\nSet with the use of String: ")
print(set1)

# Creating a Dictionary
# with Integer Keys
Dict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}
print("\nDictionary with the use of Integer Keys: ")
print(Dict)
```

**输出:**

```
Numbric data :  123
String with the use of Single Quotes: 
Welcome to the Geeks World
<class 'bool'>
<class 'bool'>

Set with the use of String: 
{'r', 'G', 'e', 'k', 'o', 's', 'F'}

Dictionary with the use of Integer Keys: 
{1: 'Geeks', 2: 'For', 3: 'Geeks'}

```

### **对象引用:**

让我们给值 5 分配一个变量 x，给变量 x 分配另一个变量 y。

## 蟒蛇 3

```
x = 5
y = x
```

当 Python 查看第一条语句时，它所做的是，首先，它创建一个对象来表示值 5。然后，它创建变量 x(如果它不存在的话)，并使它成为这个新对象 5 的引用。第二行导致 Python 创建变量 y，它没有被赋予 x，而是被用来引用 x 引用的那个对象。最终结果是变量 x 和 y 最终引用了同一个对象。这种多个名称引用同一个对象的情况，在 Python 中被称为 **【共享引用】** 。
现在，如果我们写:

## 蟒蛇 3

```
x = 'Geeks'
```

这个语句做了一个新的对象来表示‘Geeks’，并做了 x 来引用这个新对象。

### **创建对象(或类类型的变量):**

详见[类、对象、成员](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-1-class-and-its-members/)。

## 蟒蛇 3

```
# Python program to show that the variables with a value 
# assigned in class declaration, are class variables and
# variables inside methods and constructors are instance
# variables.

# Class for Computer Science Student
class CSStudent:

    # Class Variable
    stream = 'cse'            

    # The init method or constructor
    def __init__(self, roll):

        # Instance Variable    
        self.roll = roll       

# Objects of CSStudent class
a = CSStudent(101)
b = CSStudent(102)

print(a.stream)  # prints "cse"
print(b.stream)  # prints "cse"
print(a.roll)    # prints 101

# Class variables can be accessed using class
# name also
print(CSStudent.stream) # prints "cse"    
```

**Output**

```
cse
cse
101
cse

```