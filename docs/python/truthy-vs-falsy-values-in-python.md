# Python 中的真值 vs 假值

> 原文:[https://www . geesforgeks . org/truthy-vs-falsy-values-in-python/](https://www.geeksforgeeks.org/truthy-vs-falsy-values-in-python/)

在本文中，我们将了解 Python 中 **Truthy** 和 **Falsy** 值的概念，并了解如何通过使用 **bool()** 内置 Python 函数来确定一个值是 **Truthy** 还是 **Falsy** 。

现在，让我们从以下两个代码开始:

## python 3

T0T6】

**输出:**

```py
7

```

让我们将数字的值更改为 0

T2T4

```py
number = 0
if number:
  print(number)
```

T5

**输出:**

```py
There is no Output

```

你有没有想过为什么上面的代码在**号**不是表达式的情况下成功运行？

答案在于**真实**和**虚假**价值观的概念。

## 真实与虚假的价值观

在 Python 中，单个值可以评估为**真**或**假**。

基本规则是:

*   A value evaluated as false is considered as **false** .
*   The value evaluated as true is regarded as **true value** .

**虚假值包括:**

**1)序列和集合:**

*   空列表[]
*   空元组()
*   空词典{}
*   空集集()
*   空字符串" "
*   空范围范围(0)

**2)数字:任意数字类型的零。**

*   Integer: 0
*   Floating point number: 0.0
*   Plural: 0j

**3)常量:**

*   without
*   false

**Falsy** 值是当**号**的值为零时，在我们的初始示例中没有输出的原因。

**真值包括:**

*   Non-empty sequence or set (list, tuple, string, dictionary, set).
*   A value that is not zero.
*   No change: true

这就是为什么在我们的初始示例中打印的值，因为它的一个**数字**的值是 **7** (一个**真值**值):

## **内置 bool()功能**

您可以通过内置的**[**bool()**](https://www.geeksforgeeks.org/bool-in-python/)**功能来检查一个值是**真值还是**假值。该函数使用标准的真值测试程序********

> ********语法:** bool(参数)******

****，将一个值返回或转换为布尔值，即 True 或 False****

您只需要将该值作为参数传递。

**例:**

## 蟒 3

```py
bool(7)
# True

bool(0)
 #False

bool([])
# False

bool({7,4})
#True

bool(-4)
# True

bool(0.0)
# False

bool(None)
# False

bool(1)
#True

bool(range(0))
# False

bool(set())
# False

bool([1,2,3,4])
# True
```

**输出:**

```py
True
False
False
True
True
False
False
True
False
False
True

```

现在让我们看一个程序，以更好地理解真理和谬误的价值。

**例:**

## 蟒 3

```py
# define a function for checking
# number is even or odd
def even_odd(number):

  if number % 2: 

     # since num % 2 is equal to 1
     # which is Truthy Value
     return 'odd number'

  else: 

     # since num%2 is equal to 0
     # which is Falsy Value.
     return 'even number'

result1 = even_odd(7)

# prints odd
print(result1) 

result2 = even_odd(4)

# prints even
print(result2) 
```

**输出:**

```py
odd number
even number

```

由于在第一个函数调用中 num % 2 等于 1，即 **Truthy** 值，因此输出为**“奇数”**，而在第二个函数调用中 num % 2 等于 0，即 **Falsy** 值，因此输出为**“偶数”。**