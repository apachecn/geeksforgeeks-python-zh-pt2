# Python 中的简单钻石图案

> 原文:[https://www . geesforgeks . org/simple-diamond-pattern-in-python/](https://www.geeksforgeeks.org/simple-diamond-pattern-in-python/)

给定一个整数 n，任务是编写一个 python 程序，使用循环和数学公式打印钻石。n 的最小值应该大于 4。

**示例:**

```
For size = 5

  * * *   
* * * * * 
  * * *   
    *  

For size = 8

  * * * * * *   
* * * * * * * * 
  * * * * * *   
    * * * *     
      * *       

For size = 11

  * * * * * * * * *   
* * * * * * * * * * * 
  * * * * * * * * *   
    * * * * * * *     
      * * * * *       
        * * *         
          *           
```

**进场:**

使用以下步骤:

*   使用两个循环形成(size/2+2) x 大小的工作表。
*   应用 if-else 条件打印星星。
*   对休息空间应用其他条件。

下面是上述方法的实现:

**例 1:**

## 蟒蛇 3

```
# define the size (no. of columns)
# must be odd to draw proper diamond shape
size = 8

# initialize the spaces
spaces = size

# loops for iterations to create worksheet
for i in range(size//2+2):
    for j in range(size):

        # condition to left space
        # condition to right space
        # condition for making diamond
        # else print *
        if j < i-1:
            print(' ', end=" ")
        elif j > spaces:
            print(' ', end=" ")
        elif (i == 0 and j == 0) | (i == 0 and j == size-1):
            print(' ', end=" ")
        else:
            print('*', end=" ")

    # increase space area by decreasing spaces
    spaces -= 1

    # for line change
    print()
```

**输出:**

```
  * * * * * *   
* * * * * * * * 
  * * * * * *   
    * * * *     
      * *       
```

**例 2:**

## 蟒蛇 3

```
# define the size (no. of columns)
# must be odd to draw proper diamond shape
size = 11

# initialize the spaces
spaces = size

# loops for iterations to create worksheet
for i in range(size//2+2):
    for j in range(size):

        # condition to left space
        # condition to right space
        # condition for making diamond
        # else print ^
        if j < i-1:
            print(' ', end=" ")
        elif j > spaces:
            print(' ', end=" ")
        elif (i == 0 and j == 0) | (i == 0 and j == size-1):
            print(' ', end=" ")
        else:
            print('*', end=" ")

    # increase space area by decreasing spaces
    spaces -= 1

    # for line change
    print()
```

**输出:**

```
  * * * * * * * * *   
* * * * * * * * * * * 
  * * * * * * * * *   
    * * * * * * *     
      * * * * *       
        * * *         
          *          
```