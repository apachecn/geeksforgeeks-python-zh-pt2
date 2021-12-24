# 递归确定给定数字是偶数还是奇数的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-确定给定数字是偶数还是奇数的程序-递归/](https://www.geeksforgeeks.org/python-program-to-determine-whether-a-given-number-is-even-or-odd-recursively/)

在本文中，我们将看到如何使用递归方法编写程序来查找给定的数字是偶数还是奇数。如果这个数字在 Python 中返回真或假。

为此，我们使用名为[**的运算符**](https://www.geeksforgeeks.org/what-is-a-modulo-operator-in-python/) **。**这个运算符用在运算中，当我们需要计算那个数除以任何除数时的余数。

*   **偶数**:能被 2 整除的数，因此余数为 0
*   **奇数:**不能被 2 整除的数，因此余数为 1

**示例:**

```py
Input: 2
Output: True
Explanation : 2 % 2==0 So True

Input: 5
Output: False 
Explanation : 2 % 2 != 0 So, False
```

**方法#1:**

**进场:**

*   我们使用的概念是通过用数字-2 减去数字来得到余数，而不使用模数运算符
*   如果最后，我们得到任何余数，那么这个数是奇数，并为这个数返回假
*   否则该数字为偶数，并为该数字返回 True

## 蟒蛇 3

```py
# defining the function having the one parameter as input
def evenOdd(n):

    #if remainder is 0 then num is even
    if(n==0):
        return True

    #if remainder is 1 then num is odd
    elif(n==1):
        return False
    else:
        return evenOdd(n-2)

# Input by geeks
num=3
if(evenOdd(num)):
    print(num,"num is even")
else:
    print(num,"num is odd")
```

**输出:**

```py
3 num is odd
```

**方法#2:**

我们使用模数运算符来寻找偶数或奇数，就像如果 num % 2 == 0，则余数为 0，因此给定的数字为偶数，并返回 True

否则，如果 num % 2！= 0，则余数不为零，因此给定的数字是奇数，并返回 False

## 蟒蛇 3

```py
# defining the function having
# the one parameter as input
def evenOdd(n):

    #if remainder is 0 then num is even
    if(n % 2 == 0):
        return True

    #if remainder is 1 then num is odd
    elif(n %2 != 0):
        return False
    else:
        return evenOdd(n)

# Input by geeks
num = 3
if(evenOdd( num )):
    print(num ,"num is even")
else:
    print(num ,"num is odd")
```

**输出:**

```py
3 num is odd
```

**方法#3:** 打印范围(a，b)的所有偶数

这里我们将打印函数偶数(n)中给定范围 n 的所有偶数

## 蟒蛇 3

```py
# writing the function having the range
# and printing the even in that range
def evenOdd(a,b):
    if(a>b):
        return
    print(a ,end=" ")
    return evenOdd(a+2,b)

# input by geeks
x=2
y=10
if(x % 2 ==0):
    x=x

else:

    # if the number x is odd then
    # add 1 the number into it to
    # avoid any error to make it even
    x+=1
evenOdd(x,y)
```

**输出:**

```py
2 4 6 8 10
```