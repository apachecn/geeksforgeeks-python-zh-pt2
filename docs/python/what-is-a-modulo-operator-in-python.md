# Python 中的模运算符(%)是什么？

> 原文:[https://www . geesforgeks . org/什么是 python 中的模运算符/](https://www.geeksforgeeks.org/what-is-a-modulo-operator-in-python/)

当我们看到“%”时，首先想到的是“百分比符号”，但从计算机语言的角度来看，这个符号实际上有另一个名称和含义。在计算中，**模运算** (%)求一个数除以另一个数后的**余数**或**符号余数**(称为运算的模)。

给定两个正数 a 和 n，模 n (a % n，缩写为 a **mod** n)是 a 除以 n 的**欧几里德除法**的余数，其中 a 是被除数，n 是除数。

基本上，Python 模运算用于获取除法的余数。模运算符( **%** )与 **+** 、**–**、 **/** 、 ***** 、 ****** 、**/**一起被视为算术运算。在大多数语言中，这个模运算符的两个操作数都必须是整数。但是 Python 模在这种情况下是通用的。操作数可以是**整数**或**浮点**。

**语法:**

```py
a % b

```

这里，a 除以 b，然后返回除法的余数。

**代码:**

## 蟒蛇 3

```py
# inputs
a = 13
b = 5

# Stores the remainder obtained 
# when dividing a by b, in c
c = a % b      
print(a, "mod", b, "=",
      c, sep = " ")

# inputs
d = 15.0
e = 7.0

# Stores the remainder obtained 
# when dividing d by e, in f
f = d % e
print(d, "mod", e, "=", 
      f, sep = " ")
```

**输出:**

```py
13 mod 5 = 3
15.0 mod 7.0 = 1.0

```

这是一个简单的例子，展示了语法的使用，以及模运算符执行的基本操作。假设，当除以一个固定的数 k 时，我们想计算从 1 到 n 的每个数的余数。

## 蟒蛇 3

```py
# function is defined for finding out 
# the remainder of every number from 1 to n
def findRemainder(n, k):

  for i in range(1, n + 1):
    # rem will store the remainder 
    # when i is divided by k.
    rem = i % k  

    print(i, "mod", k, "=", 
          rem, sep = " ")

# Driver code
if __name__ == "__main__" :

  # inputs
  n = 5
  k = 3

  # function calling
  findRemainder(n, k)
```

**输出:**

```py
1 mod 3 = 1
2 mod 3 = 2
3 mod 3 = 0
4 mod 3 = 1
5 mod 3 = 2

```

## 例外

python 模运算的唯一例外是**零除法错误**。如果模运算符的除法器操作数变为**零**，就会出现这种情况。这意味着**右操作数不能为零**。让我们看下面的代码来了解这个 python 异常。

## 蟒蛇 3

```py
# inputs
a = 14
b = 0

# exception handling
try:
    print(a, 'mod', b, '=',
          a % b, sep = " ")

except ZeroDivisionError as err:
    print('Cannot divide by zero!' +
          'Change the value of the right operand.')
```

**输出:**

```py
Cannot divide by zero! Change the value of the right operand.

```