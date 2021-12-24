# Python 数字库

> 原文:[https://www.geeksforgeeks.org/python-numerize-library/](https://www.geeksforgeeks.org/python-numerize-library/)

**numericize**是 python 库，用于将大量数字显示为可读格式。它基本上将数字格式转换成紧凑的短格式。没有必要显示数字后面有多少个零。它自己检查系数后面的数字，然后相应地以紧凑的简短形式提供输出。

#### 关键特征

它增强了理解，因为不需要在数字系数后面写一些零(也称为尾随零)。

**示例:**

```
1 -> 1
10 -> 10
100 -> 100
1000 -> 1k
1500 -> 1.5k
1000000 -> 1M
1000000000 -> 1B
1000000000000 -> 1T

```

**注:**

*   这里 k 代表千(即系数将有 3 个尾随数字)，M 代表百万(即系数将有 6 个尾随数字)，B 代表十亿(即系数将有 9 个尾随数字)，T 代表万亿(即系数将有 12 个尾随数字)。
*   它最多只能转换 100T 的数字。

#### 安装库

要安装此模块，请在终端中键入以下命令。

```
pip install numerize 
```

**例 1:**

```
from numerize import numerize 

a = numerize.numerize(100)
print(a)

a = numerize.numerize(1000)
print(a)

a = numerize.numerize(1500)
print(a)

a = numerize.numerize(1000000)
print(a)

a = numerize.numerize(1123456)
print(a)

a = numerize.numerize(10000000000)
print(a)
```

**输出:**

```
100
1k
1.5k
1M
1.12M
10B

```

**例 2:**

```
from numerize import numerize 

# Here we can also get number upto 
# any decimal place
a = numerize.numerize(1234567.12, 2)
print(a)

a = numerize.numerize(1247854, 4)
print(a)

a = numerize.numerize(12134.123, 3)
print(a)
```

**输出:**

```
1.23M
1.2479M
12.134K

```