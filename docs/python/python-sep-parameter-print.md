# Python |打印中的 sep 参数()

> 原文:[https://www.geeksforgeeks.org/python-sep-parameter-print/](https://www.geeksforgeeks.org/python-sep-parameter-print/)

Python 中 print()函数的参数之间的分隔符默认为空格(软空格功能)，可以根据我们的选择修改为任意字符、整数或字符串。“sep”参数用于实现同样的目的，它仅在 python 3.x 或更高版本中存在。它也用于格式化输出字符串。

**示例:**

## 蟒蛇 3

```
#code for disabling the softspace feature
print('G','F','G', sep='')

#for formatting a date
print('09','12','2016', sep='-')

#another example
print('pratik','geeksforgeeks', sep='@')
```

**输出:**

```
GFG
09-12-2016
pratik@geeksforgeeks
```

sep 参数与 [end](https://www.geeksforgeeks.org/gfact-50-python-end-parameter-in-print/) 参数一起使用时，会产生令人敬畏的结果。结合 sep 和[结束](https://www.geeksforgeeks.org/gfact-50-python-end-parameter-in-print/)参数的一些例子。

## 蟒蛇 3

```
print('G','F', sep='', end='')
print('G')
#\n provides new line after printing the year
print('09','12','2016', sep='-', end='\n')

print('prtk','agarwal', sep='', end='@')
print('geeksforgeeks')
```

**输出:**

```
GFG
09-12-2016
prtkagarwal@geeksforgeeks
```

注意:请在联机 ide 中将语言从 Python 改为 Python 3。
在你的 cmd ( windows)或终端(linux )
中输入 python，进入你的交互式 python ide

## 蟒蛇 3

```
#import the below module and see what happens
import antigravity
#NOTE - it wont work on online ide
```

本文由 [**Pratik Agarwal**](https://www.facebook.com/Pratik.Agarwal01) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。