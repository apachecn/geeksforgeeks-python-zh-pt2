# sys.stdout .用 Python 编写

> 原文:[https://www.geeksforgeeks.org/sys-stdout-write-in-python/](https://www.geeksforgeeks.org/sys-stdout-write-in-python/)

这是一个内置的 Python 模块，包含特定于系统的参数，即它包含与解释器交互的变量和方法，并且也由解释器控制。

## **系统**

一个内置的文件对象，类似于 Python 中解释器的标准输出流。stdout 用于直接向屏幕控制台显示输出。输出可以是任何形式，它可以从打印语句、表达式语句甚至直接输入的提示中输出。默认情况下，流处于文本模式。事实上，无论在代码中哪里调用打印函数，它都首先被写入 sys.stdout，然后最终显示在屏幕上。

sys.stdout.write()与对象代表的目的相同，只是在交互模式下使用时，它也会打印文本中的字母数。与 print 不同，sys.stdout.write 不会在显示一个文本后切换到新行。为此，可以使用一个新的行转义字符(\n)。

**语法:**

```
sys.stdout.write(<some string text here>)

```

**例 1:**

## 蟒蛇 3

```
import sys

sys.stdout.write('gfg')
```

**Output**

```
gfg
```

**例 2:**

## 蟒蛇 3

```
# script mode
import sys

sys.stdout.write('gfg')
sys.stdout.write('geeks')
sys.stdout.write('\n')
sys.stdout.write('for geeks')
```

**Output**

```
gfggeeks
for geeks
```

stdout 也可以用来打印多个元素。不仅如此，只要支持 write()就可以将这个 stdout 分配给另一个变量。

**例 3:**

## 蟒蛇 3

```
import sys

# stdout assigned to a variable
var = sys.stdout
arr = ['geeks', 'for', 'geeks']

# printing everything in the same line
for i in arr:
    var.write(i)

# printing everything in a new line
for j in arr:
    var.write('\n'+j)
```

**输出:**

```
geeksforgeeks
geeks
for
geeks

```