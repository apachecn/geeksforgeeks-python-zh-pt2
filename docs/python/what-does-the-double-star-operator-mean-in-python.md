# Python 中的双星运算符是什么意思？

> 原文:[https://www . geesforgeks . org/python 中的双星运算符是什么意思/](https://www.geeksforgeeks.org/what-does-the-double-star-operator-mean-in-python/)

双星或(**)是 Python 语言中的算术运算符(Like +，-，*，**，/，/，%)之一。它也被称为动力操作员。

### **算术运算符的优先级是什么？**

算术运算符遵循与数学中相同的优先规则，它们是:先执行指数运算，然后执行乘法和除法，然后是加法和减法。

**算术运算符在递减模式下的优先级顺序:**

```
()   >>   **   >>   *  >>  /  >>  //  >>  %   >>   +   >>   -

```

### 双星运算符的用途:

**作为幂运算子**

对于数值数据类型，双星号(**)被定义为指数运算符:

**例:**

## 蟒 3

```
# Python code to Demonstrate the Exponential Operactor

a = 2
b = 5

# using double asterisk operator
c = a**b
print(c)

# using double asterisk operator
z = 2 * (4 ** 2) + 3 * (4 ** 2 - 10)
print(z)
```

**输出:**

```
32
50
```

**作为函数和方法中的参数**

在函数定义中，双星号也称为 ***kwargs* 。他们过去常常把一个关键字、可变长度的参数字典传递给一个函数。两个星号(**)是这里的重要元素，因为单词 *kwargs* 是常规使用的，尽管语言没有强制执行。

首先，让我们简单地打印出传递给函数的 ***kwargs* 参数。为此，我们将创建一个简短的函数:

#### 示例:

## 蟒蛇 3

```
# Python Program to create a function to get a dictionary of names.
# Here, we will start with a dictionary of three names

def function(**kwargs):
    for key, value in kwargs.items():
        print("The value of {} is {}".format(key, value))

function(name_1="Shrey", name_2="Rohan", name_3="Ayush")
```

**输出:**

```
The value of name_1 is Shrey
The value of name_2 is Rohan
The value of name_3 is Ayush
```

下面是另一个例子，我们将向函数传递额外的参数，以显示 ***kwargs* 将接受任意数量的参数:

## python 3

```
# Python Program to create a function to get a dictionary of as many names
# you want to include in your Dictionary

def function(**kwargs):
    for key, value in kwargs.items():
        print("The value of {} is {}".format(key, value))

function(
    name_1="Ayush",
    name_2="Aman",
    name_3="Harman",
    name_4="Babber",
    name_5="Striver",
)
```

**输出:**

```
The value of name_1 is Ayush
The value of name_2 is Aman
The value of name_3 is Harman
The value of name_4 is Babber
The value of name_5 is Striver
```

### 结论:

使用 ***kwargs* 为我们提供了在程序中使用关键字参数的灵活性。当我们使用 ***kwargs* 作为参数时，我们不需要知道我们最终希望传递给函数多少个参数。创建接受 ***kwargs* 的函数最适合在参数列表中输入数量相对较少的情况下使用。