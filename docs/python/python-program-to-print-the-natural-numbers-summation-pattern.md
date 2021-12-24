# 打印自然数求和模式的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序打印-自然数-求和-模式/](https://www.geeksforgeeks.org/python-program-to-print-the-natural-numbers-summation-pattern/)

给定一个自然数 n，任务是编写一个 Python 程序，首先找到前 n 个自然数的和，然后将每一步打印为一个模式。

> **输入:** 5
> 
> **输出:**
> 
> 1 = 1
> 1+2 = 3
> 1+2+3 = 6
> 1+2+3+4 = 10
> 1+2+3+4+5 = 15
> 
> **输入:** 10
> 
> **输出:**
> 
> 1 = 1
> 
> 1 + 2 = 3
> 
> 1 + 2 + 3 = 6
> 
> 1 + 2 + 3 + 4 = 10
> 
> 1 + 2 + 3 + 4 + 5 = 15
> 
> 1 + 2 + 3 + 4 + 5 + 6 = 21
> 
> 1 + 2 + 3 + 4 + 5 + 6 + 7 = 28
> 
> 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 = 36
> 
> 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 = 45
> 
> 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10 = 55

**进场:**

*   输入 n
*   使用两个循环:
    *   j 范围为 1 至 n。
    *   I 范围在 1 到 j 之间。
*   将 I 的值附加到列表时，打印 I 和'+'运算符的值。
*   然后在列表中找到元素的和。
*   用总和打印“=”。
*   出口。

**程序:**

## 蟒蛇 3

```py
# Inputing Natural Number
number = int(input("Enter the Natural Number: "))

# j ranges from 1 to n
for j in range(1, number+1):

    # Initializing List
    a = []

    # i loop ranges from 1 to j
    for i in range(1, j+1):
        print(i, sep=" ", end=" ")
        if(i < j):
            print("+", sep=" ", end=" ")
        a.append(i)
    print("=", sum(a))

print()
```

**输出:**

> 输入自然数:5
> 
> 1 = 1
> 
> 1 + 2 = 3
> 
> 1 + 2 + 3 = 6
> 
> 1 + 2 + 3 + 4 = 10
> 
> 1 + 2 + 3 + 4 + 5 = 15