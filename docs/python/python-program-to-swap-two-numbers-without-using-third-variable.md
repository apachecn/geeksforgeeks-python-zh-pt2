# Python 程序在不使用第三个变量的情况下交换两个数字

> 原文:[https://www . geesforgeks . org/python-程序到交换-两个数字-不使用第三个变量/](https://www.geeksforgeeks.org/python-program-to-swap-two-numbers-without-using-third-variable/)

给定两个变量 n1 和 n2。任务是在不使用第三个变量的情况下交换两个变量的值。
**例:**

```py
X : 10
Y : 20

After swapping X and Y, we get :

X : 20
Y : 10

```

```py
 A : 'Hello'
 B : 'World'

After swapping A and B, we get : 

 A : 'World'
 B : 'Hello'

```

**方法 1 :-使用简单的内置方法**

```py
left , right = right , left 

```

此方法适用于任何数据类型值，如 string、int、float，并且易于使用。

## 计算机编程语言

```py
# Python code to swap two numbers
# without using another variable

x = 5
y = 7

print ("Before swapping: ")
print("Value of x : ", x, " and y : ", y)

# code to swap 'x' and 'y'
x, y = y, x

print ("After swapping: ")
print("Value of x : ", x, " and y : ", y)
```

**输出:**

```py
Before swapping: 
Value of x :  5  and y :  7
After swapping: 
Value of x :  7  and y :  5    

```

**方法 2 :-使用逐位异或运算符**

```py
x ^= y
y ^= x
x ^= y

```

此方法仅适用于整数，并且速度更快，因为此方法使用位操作(对于相同的值，输出= 0，对于不同的值，输出= 1)。

## 计算机编程语言

```py
# Python code to swap two numbers
# using Bitwise XOR method

x = 5  # x = 0101
y = 10 # y = 1010

print ("Before swapping: ")
print("Value of x : ", x, " and y : ", y)

# Swap code
x ^= y # x = 1111, y = 1010
y ^= x # y = 0101, x = 1111
x ^= y # x = 1010, y = 0101

print ("After swapping: ")
print("Value of x : ", x, " and y : ", y)
```

**输出:**

```py
Before swapping: 
Value of x :  5  and y :  10
After swapping: 
Value of x :  10  and y :  5

```

**方法 3 :-使用加减法运算符**

```py
x = x + y 
y = x - y
x = x - y

```

此方法适用于具有数值的变量。

## 计算机编程语言

```py
# Python code to swap two numbers
# using + and - operators

x = 5.4
y = 10.3

print ("Before swapping: ")
print("Value of x : ", x, " and y : ", y)

# Swap code
x = x + y # x = 15.7, y = 10.3
y = x - y # x = 15.7, y = 5.4
x = x - y # x = 10.3, y = 5.4

print ("After swapping: ")
print("Value of x : ", x, " and y : ", y)
```

**输出:**

```py
Before swapping: 
Value of x :  5.4  and y :  10.3
After swapping: 
Value of x :  10.3  and y :  5.4

```

**方法 4 :-使用除法和乘法运算符**

```py
x = x * y
y = x / y
x = x / y

```

此方法适用于数值不是 0 的变量。

## 计算机编程语言

```py
# Python code to swap two numbers
# using / and * operators

x = 5.4
y = 10.3

print ("Before swapping: ")
print("Value of x : ", x, " and y : ", y)

# Swap code
x = x * y # x = 55.62, y = 10.3
y = x / y # x = 55.62, y = 5.4
x = x / y # x = 10.3, y = 5.4

print ("After swapping: ")
print("Value of x : ", x, " and y : ", y)
```

**输出:**

```py
Before swapping: 
Value of x :  5.4  and y :  10.3
After swapping: 
Value of x :  10.3  and y :  5.4

```

**方法 4:同时使用按位运算符和算术运算符:**

## 蟒蛇 3

```py
# python program to swap two numbers
# using bitwise addition for swapping

x = 5;
y = 10;

print ("Before swapping: ") ;
print("Value of x : ", x, " and y : ", y) ;

# same as x = x + y
x = (x & y) + (x|y) ;

#vsame as y = x - y
y = x + (~y) + 1 ;

# same as x = x - y
x = x + (~y) + 1 ;

print ("After swapping: ")
print("Value of x : ", x, " and y : ", y)

# This code is contributed by bunnyram19
```

**输出:**

```py
Before swapping: 
Value of x :  5  and y :  10
After swapping: 
Value of x :  10  and y :  5

```