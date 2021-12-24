# Python |使用时间()模块生成模式

> 原文:[https://www . geesforgeks . org/python-模式-生成-使用-时间-模块/](https://www.geeksforgeeks.org/python-pattern-generation-using-time-module/)

本文旨在使用 python 中的 **time()模块**打印图案。
**例:**

> **输入:**
> 5
> **输出:**
> 5 个使用时间的模式，共 5 行
> 
> **输入:**
> 4
> **输出:**
> 5 个模式使用时间为 4 行，但对于钻石如果你
> 会输入偶数行，它会自动做(行+1)

**代码:生成模式的 Python 程序**

```
# Print triangles by giving the number of stars:

# For Diamond, an odd number of stars will give a better result,
# If the number is even then for diamond pattern,
# it will automatically do (row + 1):

import time

n = 5

print("----------Right Angled Triangle Type 1----------")

def right_angle_triangle1(n):

    for i in range(1, n + 1):
        for j in range(i):
            time.sleep(0.05)
            print("*", end ="")
        print()

right_angle_triangle1(n)

print()

print("----------Right Angled Triangle Type 2----------")

def right_angle_triangle2(n):

    for i in range(1, n + 1):
        for j in range(n-i):
            time.sleep(0.05)
            print(" ", end ="")
        for k in range(i):
            time.sleep(0.05)
            print("*", end ="")
        print()
right_angle_triangle2(n)

print()

print("----------Equilateral Triangle----------")

def equilateral_triangle(n):

    for i in range(1, n + 1):
        for j in range(n-i):
            time.sleep(0.05)
            print(" ", end ="")
        for k in range(2 * i-1):
            time.sleep(0.05)
            print("*", end ="")
        print()
equilateral_triangle(n)

print()

print("----------Square----------")

def square(n):

    for i in range(1, n + 1):
        for j in range(1, n + 1):
            time.sleep(0.05)
            print("*", end ="")
        print()
square(n)

print()

print("----------Diamond----------")

def diamond(n):

    cell = n//2 + 1
    for i in range(1, cell + 1): 
        for j in range(cell-i):     
            time.sleep(0.05)
            print(" ", end ="")
        for k in range(2 * i-1):
            time.sleep(0.05)
            print("*", end ="")
        print()

    for i in range(cell-1, 0, -1):
        for j in range(cell-i):
            time.sleep(0.05)
            print(" ", end ="")

        for k in range(2 * i-1):
            time.sleep(0.05)
            print("*", end ="")
        print()
diamond(n)
```

**输出:**

```
----------Right Angled Triangle Type 1----------
*
**
***
****
*****

----------Right Angled Triangle Type 2----------
    *
   **
  ***
 ****
*****

----------Equilateral Triangle----------
    *
   ***
  *****
 *******
*********

----------Square----------
*****
*****
*****
*****
*****

----------Diamond----------
  *
 ***
*****
 ***
  *

```