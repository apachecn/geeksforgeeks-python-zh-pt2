# Python 程序向右旋转 n 个数字 1

> 原文:[https://www . geesforgeks . org/python-program-to-right-rotate-n-numbers-by-1/](https://www.geeksforgeeks.org/python-program-to-right-rotate-n-numbers-by-1/)

给定一个数字 n。任务是打印 n 个整数 n 次(从 1 开始)，并在每次迭代后向右旋转整数。
**例:**

```py
Input : 6
Output :
1 2 3 4 5 6
2 3 4 5 6 1
3 4 5 6 1 2
4 5 6 1 2 3
5 6 1 2 3 4
6 1 2 3 4 5

Input : 3
Output :
1 2 3 
2 3 1 
3 1 2

```

下面是实现。

## 蟒蛇 3

```py
def print_pattern(n):
    for i in range(1, n+1, 1):
        for j in range(1, n+1, 1):
            # check that if index i is
            # equal to j
            if i == j:

                print(j, end=" ")
                # if index i is less than j
                if i <= j:

                    for k in range(j+1, n+1, 1):
                        print(k, end=" ")

                for p in range(1, j, 1):
                    print(p, end=" ")

        # print new line
        print()

# Driver's code
print_pattern(3)
```

**输出:**

```py
1 2 3 
2 3 1 
3 1 2 

```