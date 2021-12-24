# Python–打印心形图案

> 原文:[https://www.geeksforgeeks.org/python-print-heart-pattern/](https://www.geeksforgeeks.org/python-print-heart-pattern/)

给定一个偶数整数输入，任务是编写一个 Python 程序，使用循环和数学公式打印心脏。

#### 示例:

```
For n = 8

  *   *   *   *   
*       *       * 
*               * 
*     G F G     * 
  *           *   
    *       *     
      *   *       
        *

For n = 14

      * *           * *       
    *     *       *     *     
  *         *   *         *   
*             *             * 
*                           * 
*           G F G           * 
  *                       *   
    *                   *     
      *               *       
        *           *         
          *       *           
            *   *             
              *       
```

#### 方法:

使用以下步骤:

*   用两个循环组成 n×n+1 的工作表。
*   应用 if-else 条件打印星星。
*   应用 if-else 条件打印文本“GFG”。
*   对休息空间应用其他条件。

**注意:**n 的值必须大于 8

下面是上述方法的实现:

## 蟒蛇 3

```
# define size n = even only
n = 8

# so this heart can be made n//2 part left,
# n//2 part right, and one middle line
# i.e; columns m = n + 1
m = n+1

# loops for upper part
for i in range(n//2-1):
    for j in range(m):

        # condition for printing stars to GFG upper line
        if i == n//2-2 and (j == 0 or j == m-1):
            print("*", end=" ")

        # condition for printing stars to left upper
        elif j <= m//2 and ((i+j == n//2-3 and j <= m//4) \
                            or (j-i == m//2-n//2+3 and j > m//4)):
            print("*", end=" ")

        # condition for printing stars to right upper
        elif j > m//2 and ((i+j == n//2-3+m//2 and j < 3*m//4) \
                           or (j-i == m//2-n//2+3+m//2 and j >= 3*m//4)):
            print("*", end=" ")

        # condition for printing spaces
        else:
            print(" ", end=" ")
    print()

# loops for lower part
for i in range(n//2-1, n):
    for j in range(m):

        # condition for printing stars
        if (i-j == n//2-1) or (i+j == n-1+m//2):
            print('*', end=" ")

        # condition for printing GFG
        elif i == n//2-1:

            if j == m//2-1 or j == m//2+1:
                print('G', end=" ")
            elif j == m//2:
                print('F', end=" ")
            else:
                print(' ', end=" ")

        # condition for printing spaces
        else:
            print(' ', end=" ")

    print()
```

**输出:**

```

      * *           * *       
    *     *       *     *     
  *         *   *         *   
*             *             * 
*                           * 
*           G F G           * 
  *                       *   
    *                   *     
      *               *       
        *           *         
          *       *           
            *   *             
              *               
```