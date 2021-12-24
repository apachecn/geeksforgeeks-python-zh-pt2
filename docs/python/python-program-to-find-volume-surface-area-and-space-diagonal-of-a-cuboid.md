# Python 程序求长方体的体积、表面积和空间对角线

> 原文:[https://www . geesforgeks . org/python-program-to-find-volume-表面积-空间-长方体对角线/](https://www.geeksforgeeks.org/python-program-to-find-volume-surface-area-and-space-diagonal-of-a-cuboid/)

给定长方体的长度、底部和高度。任务是求长方体的表面积、体积和空间对角线。

![Cuboid-Diagram-1626191](img/7cd69b8c2b54bb39b779ba8539f2ee2d.png)

**例:**

```
Input : 
length = 9
breadth = 6
height = 10 
Output :
Surface area = 408 
volume = 540
space diagonal = 14.73 

Input :
length = 5
breadth = 4
height = 3 
Output : 
surface area = 94 
volume = 60 
space diagonal = 7.07 
```

**使用的公式:**

*   表面积= ![[2 * (l*b + b*h + h*l)]   ](img/4015a8dccf9fad9759ccb065546be659.png "Rendered by QuickLaTeX.com")

*   体积= ![[(l*b*h)]   ](img/60b1ffdcd536e5dd89942ffdff822bf6.png "Rendered by QuickLaTeX.com")

*   Spacle 对角线= ![[sqrt{( l**2 + b**2 + h**2)}]   ](img/cb3873cdd152307ec231cd6bc53ed53e.png "Rendered by QuickLaTeX.com")

下面是实现。

## 蟒蛇 3

```
# Python program to find the
# Surface area, volume and
# space diagonal of rectangular
# prism

import math

# function to calculate
# Surface area
def find_surafce_area(l, b, h):

    # formula of surface_area = 2(lb + bh + hl)
    Surface_area = 2 * ( l * b + b * h + h * l)

    # Display surface area
    print(Surface_area)

# function to find the
# Volume of rectangular
# prism
def find_volume(l, b, h):

    # formula to calculate
    # volume = (l * b*h)
    Volume = (l * b * h)

    # Display volume
    print(Volume)
    categories Most Used
 School Programming
 Aptitude
 Re
def find_space_diagonal(l, b, h):

    # formula to calculate
    # Space diagonal = square_root(l**2 + b**2 + h**2)
    Space_diagonal = math.sqrt(l**2 + b**2 + h**2)

    # display space diagonal
    print(Space_diagonal)

# Driver Code
l = 9
b = 6
h = 10

# surface area
# function call
find_surafce_area(l, b, h)

# volume function call
find_volume(l, b, h)

# Space diagonal function call
find_space_diagonal(l, b, h)

```

**输出:**

```
408
540
14.730919862656235
```