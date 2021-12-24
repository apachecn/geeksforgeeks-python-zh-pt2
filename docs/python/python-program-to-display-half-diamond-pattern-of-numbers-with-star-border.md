# Python 程序显示带有星形边框的半菱形数字图案

> 原文:[https://www . geeksforgeeks . org/python-程序到显示-半菱形-带星形边框的数字图案/](https://www.geeksforgeeks.org/python-program-to-display-half-diamond-pattern-of-numbers-with-star-border/)

给定一个数字 n，任务是编写一个 Python 程序来打印带有星形边框的半菱形数字图案。

**示例:**

```py
Input: n = 5
Output:

*
*1*
*121*
*12321*
*1234321*
*123454321*
*1234321*
*12321*
*121*
*1*
*

Input: n = 3
Output:

*
*1*
*121*
*12321*
*121*
*1*
*
```

**进场:**

*   两个 for 循环将在这个程序中运行，以便打印数字和星星。
*   首先打印*然后运行从 1 到(n+1)的循环，以升序打印最多行。
*   在本例中，for 循环*将被打印到 I，然后再有一个 for 循环将从 1 运行到 i+1，以便按升序打印数字。
*   现在将从 i-1 到 0 再运行一个循环，以便以相反的顺序打印数字。
*   现在将打印一颗星，这个 for 循环将结束。
*   现在，第二个 for 循环将从 n-1 运行到 0，以打印中间的图案，其中数字以相反的方式排列。
*   在这个 for 循环中，也将进行与第一个 for 循环相同的工作。
*   将显示所需的图案。

**以下是上述模式的实现:**

## 蟒蛇 3

```py
# function to display the pattern up to n
def display(n):  

    print("*")

    for i in range(1, n+1):
        print("*", end="")

        # for loop to display number up to i
        for j in range(1, i+1):  
            print(j, end="")

        # for loop to display number in reverse direction    
        for j in range(i-1, 0, -1):  
            print(j, end="")

        print("*", end="")
        print()

    # for loop to display i in reverse direction
    for i in range(n-1, 0, -1):
        print("*", end="")
        for j in range(1, i+1):
            print(j, end="")

        for j in range(i-1, 0, -1):
            print(j, end="")

        print("*", end="")
        print()

    print("*")

# driver code
n = 5
print('\nFor n =', n)
display(n)

n = 3
print('\nFor n =', n)
display(n)
```

**输出:**

```py
For n = 5
*
*1*
*121*
*12321*
*1234321*
*123454321*
*1234321*
*12321*
*121*
*1*
*

For n = 3
*
*1*
*121*
*12321*
*121*
*1*
*
```