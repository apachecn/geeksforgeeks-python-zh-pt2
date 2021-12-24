# Python 中的 unicode _ 常值

> 原文:[https://www.geeksforgeeks.org/unicode_literals-in-python/](https://www.geeksforgeeks.org/unicode_literals-in-python/)

Unicode 也称为通用字符集。ASCII 使用 8 位(1 字节)来表示一个字符，最多可以有 256 个(2^8)不同的组合。ASCII 的问题是它只能支持英语，但如果我们想使用另一种语言，如印地语、俄语、汉语等，该怎么办？我们没有足够的 ASCII 空间来覆盖所有这些语言和表情符号。这就是 Unicode 的由来，Unicode 为我们提供了一个巨大的表，可以存储 ASCII 表，也可以存储其他语言、符号和表情符号。

我们实际上不能直接将文本保存为 Unicode。因为 Unicode 只是文本数据的抽象表示。我们需要某种编码/映射来将每个字符映射到某个数字。如果一个字符使用超过 1 个字节(8 位)，那么所有这些字节都需要打包成一个单元(想象一个有多个项目的盒子)。这种拳法叫做 **UTF-8** 法。在 UTF-8 字符最少可以占用 8 位，在 **UTF-16** 字符最少可以占用 **16 位。UTF** 只是一个算法，把 Unicode 转换成字节，然后读回来

通常，在 python2 中，默认情况下所有字符串都被视为字节字符串，但是在 python 的较高版本中，默认情况下所有字符串都是 Unicode 字符串。因此，为了使 python 中的所有字符串都是 Unicode，我们使用了以下导入:

> from __future__ 导入 unicode 文本

如果我们使用的是旧版本的 python，我们需要从未来的包中导入 unicode 文本。这种导入将使 python2 的行为与 python3 相同。这将使代码跨 python 版本兼容。

#### Python 2

## 计算机编程语言

```py
import sys

# checking the default encoding of string
print "The default encoding for python2 is:",
sys.getdefaultencoding()
```

**输出:**

```py
The default encoding for python2 is: ascii
```

和 python2 一样，默认编码是 ASCII，我们需要将编码切换到 utf-8。

## 计算机编程语言

```py
from __future__ import unicode_literals

# creating variables to holds
# the letters in python word.
p = "\u2119"
y = "\u01b4"
t = "\u2602"
h = "\u210c"
o = "\u00f8"
n = "\u1f24"

# printing Python
# encoding to utf-8 from ascii
print(p+y+t+h+o+n).encode("utf-8")
```

**Output**

```py
ℙƴ☂ℌøἤ
```

#### 蟒蛇 3:

## 蟒蛇 3

```py
# In python3
# By default the encoding is "utf-8"
import sys

# printing the default encoding
print("The default encoding for python3 is:", sys.getdefaultencoding())

# to define string as unicode
# we need to prefix every string with u"...."
p = u"\u2119"
y = u"\u01b4"
t = u"\u2602"
h = u"\u210c"
o = u"\u00f8"
n = u"\u1f24"

# printing Python
print(p+y+t+h+o+n)
```