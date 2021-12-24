# Python 程序打印空心半菱形哈希图案

> 原文:[https://www . geesforgeks . org/python-程序到打印-空心-半菱形-哈希-模式/](https://www.geeksforgeeks.org/python-program-to-print-hollow-half-diamond-hash-pattern/)

给一个整数 **N** ，任务是打印空心半菱形图案。

**示例:**

```py
Input : 6
Output :
# 
# # 
#   # 
#     # 
#       # 
#         # 
#       # 
#     # 
#   # 
# # 
# 

Input : 7
Output :
# 
# # 
#   # 
#     # 
#       # 
#         # 
#           # 
#         # 
#       # 
#     # 
#   # 
# # 
#  

```

**方法:**
想法是将模式分成两部分:

*   **上半部分:**对于上半部分，用迭代器(I)从 1 到 n 开始 for 循环，用迭代器(j)从 1 到 I 再开始一个 For 循环。

    ```py
    # 
    # # 
    #   # 
    #     # 
    #       # 
    #         # 
    #           #  

    ```

*   **下半部分:**对于下半部分，用迭代器(n-1)1 开始 for 循环，该 For 内部的循环将保持与上半部分相同。

    ```py
    #         # 
    #       # 
    #     # 
    #   # 
    # # 
    #

    ```

*   现在我们必须检查这个条件，如果(i==j)或(j==1)，那么我们必须打印“#”，否则我们必须打印“”(空格)。

**下面是实现:**

```py
# python program to print 
# hollow half diamond star

# function to print hollow
# half diamond star
def hollow_half_diamond(N):

    # this for loop is for 
    # printing upper half 
    for i in range( 1, N + 1):
        for j in range(1, i + 1):

            # this is the condition to 
            # print "#" only on the
            # boundaries
            if i == j or j == 1:
                print("#", end =" ")

            # print " "(space) on the rest
            # of the area
            else:
                print(" ", end =" ")
        print()

    # this for loop is to print lower half
    for i in range(N - 1, 0, -1):

        for j in range(1, i + 1):

            if j == 1 or i == j:
                print("#", end =" ")

            else:
                print(" ", end =" ")

        print()

# Driver Code
if __name__ == "__main__":
    N = 7
    hollow_half_diamond( N )

```

**输出:**

```py
# 
# # 
#   # 
#     # 
#       # 
#         # 
#           # 
#         # 
#       # 
#     # 
#   # 
# # 
# 

```

**时间复杂度:** O(N^2)