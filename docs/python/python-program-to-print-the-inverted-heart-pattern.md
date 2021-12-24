# Python 程序打印倒心形图案

> 原文:[https://www . geeksforgeeks . org/python-程序-打印-倒心形图案/](https://www.geeksforgeeks.org/python-program-to-print-the-inverted-heart-pattern/)

让我们看看如何用 Python 打印一个倒心形图案。

**例:**

```
Input: 11
Output:

          *
         ***
        *****
       *******
      *********
     ***********
    *************
   ***************
  *****************
 *******************
*********************
 *********  ********
  *******    ******
   *****      **** 

Input: 15
Output:
              *
             ***
            *****
           *******
          *********
         ***********
        *************
       ***************
      *****************
     *******************
    *********************
   ***********************
  *************************
 ***************************
*****************************
 *************  ************
  ***********    **********
   *********      ********
    *******        ******
```

**进场:**

1.  Determine the heart size.
2.  Print an inverted triangle with the number of lines.
3.  Print the rest of the heart into 4 segments in another cycle.
4.  Print the blank right triangle at the beginning.
5.  Print the first trapezoid with stars.
6.  Print an empty triangle.
7.  Print the second trapezoid with stars.

## 蟒 3

```
# determining the size of the heart
size = 15

# printing the inverted triangle
for a in range(0, size):
    for b in range(a, size):
        print(" ", end = "")
    for b in range(1, (a * 2)):
        print("*", end = "")
    print("")

# printing rest of the heart
for a in range(size, int(size / 2) - 1 , -2):

    # printing the white space right-triangle
    for b in range(1, size - a, 2): 
        print(" ", end = "")

    # printing the first trapezium
    for b in range(1, a + 1):
        print("*", end = "")

    # printing the white space triangle
    for b in range(1, (size - a) + 1):
        print(" ", end = "")

    # printing the second trapezium
    for b in range(1, a):
        print("*", end = "")

    # new line
    print("")
```

**输出:**

```
              *
             ***
            *****
           *******
          *********
         ***********
        *************
       ***************
      *****************
     *******************
    *********************
   ***********************
  *************************
 ***************************
*****************************
 *************  ************
  ***********    **********
   *********      ********
    *******        ******
```