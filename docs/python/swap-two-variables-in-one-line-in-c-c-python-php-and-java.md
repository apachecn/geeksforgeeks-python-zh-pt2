# 一行互换两个变量

> 原文:[https://www . geesforgeks . org/swap-二合一变量-in-c-c-python-PHP-and-Java/](https://www.geeksforgeeks.org/swap-two-variables-in-one-line-in-c-c-python-php-and-java/)

我们已经讨论了在没有临时变量的情况下交换两个整数的不同方法。不使用库函数如何换成单行？
**Python:** 在 Python 中，有一个简单且语法规整的构造来交换变量，我们只需要写“x，y = y，x”。
**C/C++:** 下面是一个通常提供的经典解决方案

```py
// Swap using bitwise XOR (Wrong Solution in C/C++)
x ^= y ^= x ^= y; 
```

上述解决方案在 C/C++中是错误的，因为它会导致未定义的行为(编译器可以自由地以任何方式进行操作)。原因是，如果修改之间没有[序列点](https://www.geeksforgeeks.org/sequence-points-in-c-set-1/)，在表达式中多次修改变量会导致未定义的行为。
不过，我们可以用逗号来介绍顺序点。所以修改后的解决方案是

```py
// Swap using bitwise XOR (Correct Solution in C/C++)
// sequence point introduced using comma.
(x ^= y), (y ^= x), (x ^= y);
```

**Java:** 在 Java 中，子表达式求值的规则是明确定义的。左操作数总是在右操作数之前计算(更多详情参见[本](https://docs.oracle.com/javase/specs/jls/se7/html/jls-15.html))。在 Java 语言中，表示“x ^= y ^= x ^= y；”根据 Java 规则不会产生正确的结果。它使 x = 0。然而，我们可以使用“x = x ^ y ^(y = x)；”请注意，表达式是从左向右计算的。如果最初 x = 5，y = 10，则表达式相当于“x = 5 ^ 10 ^(y = 5)；”。请注意，我们不能像在 C/C++中那样在 C/C++中使用这个，它没有定义左操作数或右操作数是由任何运算符执行的(详见[本](https://www.geeksforgeeks.org/sequence-points-in-c-set-1/))。

**JavaScript:** 使用析构赋值，我们可以简单的用这一行实现交换。

> [x，y]=[y，x]

## C

```py
// C program to swap two variables in single line
#include <stdio.h>
int main()
{
    int x = 5, y = 10;
    (x ^= y), (y ^= x), (x ^= y);
    printf("After Swapping values of x and y are %d %d", x,
           y);
    return 0;
}
```

## C++

```py
// C++ code to swap using XOR
#include <bits/stdc++.h>

using namespace std;

int main()
{
    int x = 5, y = 10;
    // Code to swap 'x'  and 'y'
    // to swap two numbers in one
    // line
     x = x ^ y, y = x ^ y, x = x ^ y;
    // printing the swapped variables
    cout << "After Swapping: x = "
         << x << ", y= " << y;
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java program to swap two variables in a single line
class GFG {
    public static void main(String[] args)
    {
        int x = 5, y = 10;
        x = x ^ y ^ (y = x);
        System.out.println(
            "After Swapping values"
            +" of x and y are " + x
            + " " + y);
    }
}
```

## 计算机编程语言

```py
# Python program to swap two variables in a single line
x = 5
y = 10
x, y = y, x
print("After Swapping values of x and y are", x, y)
```

## C#

```py
// C# program to swap two
// variables in single line
using System;

class GFG {
    static public void Main()
    {
        int x = 5, y = 10;
        x = x ^ y ^ (y = x);
        Console.WriteLine("After Swapping values "
                          + "of x and y are " + x + " "
                          + y);
    }
}

// This code is contributed by aj_36
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```py
<?php
// PHP program to swap two
// variables in single line

    // Driver Code
    $x = 5;
    $y = 10;
    ($x ^= $y);
    ($y ^= $x);
    ($x ^= $y);
    echo "After Swapping values of x and y are "
                                  ,$x," ", $y;

// This code is contributed by Vishal Tripathi
?>
```

## java 描述语言

```py
<script>
// javascript program to swap two variables in single line

    let x = 5, y = 10;
    (x ^= y), (y ^= x), (x ^= y);
    document.write("After Swapping values of x and y are ", x + " ",
           y);

// This code is contributed by Surbhi Tyagi
</script>
```

**输出:**

```py
After Swapping values of x and y are 10 5
```

**替代解决方案:**

*   C++还提供了库函数交换()
*   b =(a+b)–(a = b)；[为此感谢拉杰特·米什拉]
*   a+= b –( b = a)；【感谢佐兰·达维多维奇？为此]
*   a = a * b/(b = a)[感谢 kongasricharan 的帮助]
*   a = a ^ b ^

本文由**哈什特·古普塔供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论