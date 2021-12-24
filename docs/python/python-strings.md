# 蟒蛇串

> 原文:[https://www.geeksforgeeks.org/python-strings/](https://www.geeksforgeeks.org/python-strings/)

在 Python 中，**字符串**是表示 Unicode 字符的字节数组。但是，Python 没有字符数据类型，单个字符只是长度为 1 的字符串。方括号可以用来访问字符串的元素。

## 创建字符串

Python 中的字符串可以使用单引号、双引号甚至三引号来创建。

## 蟒蛇 3

```
# Python Program for
# Creation of String

# Creating a String
# with single Quotes
String1 = 'Welcome to the Geeks World'
print("String with the use of Single Quotes: ")
print(String1)

# Creating a String
# with double Quotes
String1 = "I'm a Geek"
print("\nString with the use of Double Quotes: ")
print(String1)

# Creating a String
# with triple Quotes
String1 = '''I'm a Geek and I live in a world of "Geeks"'''
print("\nString with the use of Triple Quotes: ")
print(String1)

# Creating String with triple
# Quotes allows multiple lines
String1 = '''Geeks
            For
            Life'''
print("\nCreating a multiline String: ")
print(String1)
```

**输出:**

```
String with the use of Single Quotes: 
Welcome to the Geeks World

String with the use of Double Quotes: 
I'm a Geek

String with the use of Triple Quotes: 
I'm a Geek and I live in a world of "Geeks"

Creating a multiline String: 
Geeks
            For
            Life
```

## 在 Python 中访问字符

在 Python 中，字符串的单个字符可以通过使用索引方法来访问。索引允许负地址引用从字符串的后面访问字符，例如-1 表示最后一个字符，-2 表示倒数第二个字符，等等。

当访问超出范围的索引时，将导致**索引错误**。只允许将整数作为索引、浮点或其他类型传递，这将导致**类型错误**。

![strings](img/203d30f1df2a80440ec2feffe46978b5.png)

## 蟒蛇 3

```
# Python Program to Access
# characters of String

String1 = "GeeksForGeeks"
print("Initial String: ")
print(String1)

# Printing First character
print("\nFirst character of String is: ")
print(String1[0])

# Printing Last character
print("\nLast character of String is: ")
print(String1[-1])
```

**输出:**

```
Initial String: 
GeeksForGeeks

First character of String is: 
G

Last character of String is: 
s
```

## 字符串切片

要访问字符串中的一系列字符，可以使用切片方法。字符串中的切片是通过使用切片操作符(冒号)来完成的。

## 蟒蛇 3

```
# Python Program to
# demonstrate String slicing

# Creating a String
String1 = "GeeksForGeeks"
print("Initial String: ")
print(String1)

# Printing 3rd to 12th character
print("\nSlicing characters from 3-12: ")
print(String1[3:12])

# Printing characters between
# 3rd and 2nd last character
print("\nSlicing characters between " +
    "3rd and 2nd last character: ")
print(String1[3:-2])
```

**输出:**

```
Initial String: 
GeeksForGeeks

Slicing characters from 3-12: 
ksForGeek

Slicing characters between 3rd and 2nd last character: 
ksForGee
```

## 从字符串中删除/更新

在 Python 中，不允许更新或删除字符串中的字符。这将导致错误，因为不支持从字符串中分配或删除项目。虽然使用内置的 del 关键字可以删除整个字符串。这是因为字符串是不可变的，因此字符串的元素一旦被赋值就不能改变。只有新字符串可以重新分配给相同的名称。

#### 角色的更新:

## 蟒蛇 3

```
# Python Program to Update
# character of a String

String1 = "Hello, I'm a Geek"
print("Initial String: ")
print(String1)

# Updating a character
# of the String
String1[2] = 'p'
print("\nUpdating character at 2nd Index: ")
print(String1)
```

**错误:**

> 回溯(最后一次调用):
> 文件/home/360 bb 1830 c 83 a 918 fc 78 aa 8979195653 . py】，第 10 行，在
> String1[2] = 'p'
> 类型错误:“str”对象不支持项目分配

#### 更新整个字符串:

## 蟒蛇 3

```
# Python Program to Update
# entire String

String1 = "Hello, I'm a Geek"
print("Initial String: ")
print(String1)

# Updating a String
String1 = "Welcome to the Geek World"
print("\nUpdated String: ")
print(String1)
```

**输出:**

```
Initial String: 
Hello, I'm a Geek

Updated String: 
Welcome to the Geek World 
```

#### 删除字符:

## 蟒蛇 3

```
# Python Program to Delete
# characters from a String

String1 = "Hello, I'm a Geek"
print("Initial String: ")
print(String1)

# Deleting a character
# of the String
del String1[2]
print("\nDeleting character at 2nd Index: ")
print(String1)
```

**错误:**

> 回溯(最近一次调用最后一次):
> 文件/home/499 e96 a61e 19944 e7e 45 b7a 6e 1276742 . py】，第 10 行，在
> del String1[2]
> 中键入错误:“str”对象不支持项目删除

#### 删除整个字符串:

使用 del 关键字可以删除整个字符串。此外，如果我们试图打印字符串，这将产生一个错误，因为字符串被删除，无法打印。

## 蟒蛇 3

```
# Python Program to Delete
# entire String

String1 = "Hello, I'm a Geek"
print("Initial String: ")
print(String1)

# Deleting a String
# with the use of del
del String1
print("\nDeleting entire String: ")
print(String1)
```

**错误:**

> 回溯(最后一次调用):
> 文件/home/e4b 8 f 2170 f 140 da 99 D2 Fe 57 d9 D8 c6a 94 . py】，第 12 行，在
> 打印(String1)
> 名称中错误:未定义名称“String1”

## Python 中的转义序列

当打印带有单引号和双引号的字符串时，会导致**语法错误**，因为字符串已经包含单引号和双引号，因此不能使用这两个选项进行打印。因此，要打印这样的字符串，要么使用三引号，要么使用转义序列来打印这样的字符串。

转义序列以反斜杠开头，可以有不同的解释。如果使用单引号来表示字符串，那么字符串中出现的所有单引号都必须转义，双引号也是如此。

## 蟒蛇 3

```
# Python Program for
# Escape Sequencing
# of String

# Initial String
String1 = '''I'm a "Geek"'''
print("Initial String with use of Triple Quotes: ")
print(String1)

# Escaping Single Quote
String1 = 'I\'m a "Geek"'
print("\nEscaping Single Quote: ")
print(String1)

# Escaping Double Quotes
String1 = "I'm a \"Geek\""
print("\nEscaping Double Quotes: ")
print(String1)

# Printing Paths with the
# use of Escape Sequences
String1 = "C:\\Python\\Geeks\\"
print("\nEscaping Backslashes: ")
print(String1)
```

**输出:**

```
Initial String with use of Triple Quotes: 
I'm a "Geek"

Escaping Single Quote: 
I'm a "Geek"

Escaping Double Quotes: 
I'm a "Geek"

Escaping Backslashes: 
C:\Python\Geeks\
```

要忽略字符串中的转义序列，可以使用 **r** 或 **R** ，这意味着字符串是一个原始字符串，其中的转义序列将被忽略。

## 蟒蛇 3

```
# Printing Geeks in HEX
String1 = "This is \x47\x65\x65\x6b\x73 in \x48\x45\x58"
print("\nPrinting in HEX with the use of Escape Sequences: ")
print(String1)

# Using raw String to
# ignore Escape Sequences
String1 = r"This is \x47\x65\x65\x6b\x73 in \x48\x45\x58"
print("\nPrinting Raw String in HEX Format: ")
print(String1)
```

**输出:**

```
Printing in HEX with the use of Escape Sequences: 
This is Geeks in HEX

Printing Raw String in HEX Format: 
This is \x47\x65\x65\x6b\x73 in \x48\x45\x58
```

## 字符串的格式

Python 中的字符串可以使用 [format()](https://www.geeksforgeeks.org/python-string-format-method/) 方法进行格式化，这是一个非常通用和强大的格式化字符串的工具。String 中的 Format 方法包含大括号{}作为占位符，可以根据位置或关键字保存参数以指定顺序。

## 蟒蛇 3

```
# Python Program for
# Formatting of Strings

# Default order
String1 = "{} {} {}".format('Geeks', 'For', 'Life')
print("Print String in default order: ")
print(String1)

# Positional Formatting
String1 = "{1} {0} {2}".format('Geeks', 'For', 'Life')
print("\nPrint String in Positional order: ")
print(String1)

# Keyword Formatting
String1 = "{l} {f} {g}".format(g='Geeks', f='For', l='Life')
print("\nPrint String in order of Keywords: ")
print(String1)
```

**输出:**

```
Print String in default order: 
Geeks For Life

Print String in Positional order: 
For Geeks Life

Print String in order of Keywords: 
Life For Geeks
```

二进制、十六进制等整数。，并且可以使用格式说明符对浮点数进行舍入或以指数形式显示。

## 蟒蛇 3

```
# Formatting of Integers
String1 = "{0:b}".format(16)
print("\nBinary representation of 16 is ")
print(String1)

# Formatting of Floats
String1 = "{0:e}".format(165.6458)
print("\nExponent representation of 165.6458 is ")
print(String1)

# Rounding off Integers
String1 = "{0:.2f}".format(1/6)
print("\none-sixth is : ")
print(String1)
```

**输出:**

```
Binary representation of 16 is 
10000

Exponent representation of 165.6458 is 
1.656458e+02

one-sixth is : 
0.17
```

字符串可以使用格式说明符左对齐()或右对齐(center(^)，用冒号(:)分隔。

## 蟒蛇 3

```
# String alignment
String1 = "|{:<10}|{:^10}|{:>10}|".format('Geeks', 'for', 'Geeks')
print("\nLeft, center and right alignment with Formatting: ")
print(String1)

# To demonstrate aligning of spaces
String1 = "\n{0:^16} was founded in {1:<4}!".format("GeeksforGeeks", 2009)
print(String1)
```

**输出:**

```
Left, center and right alignment with Formatting: 
|Geeks     |   for    |     Geeks|

 GeeksforGeeks   was founded in 2009 !
```

通过使用 **%** 运算符，在不使用格式方法的情况下完成了旧样式格式

## 蟒蛇 3

```
# Python Program for
# Old Style Formatting
# of Integers

Integer1 = 12.3456789
print("Formatting in 3.2f format: ")
print('The value of Integer1 is %3.2f' % Integer1)
print("\nFormatting in 3.4f format: ")
print('The value of Integer1 is %3.4f' % Integer1)
```

**输出:**

```
Formatting in 3.2f format: 
The value of Integer1 is 12.35

Formatting in 3.4f format: 
The value of Integer1 is 12.3457
```

**有用的字符串操作**

*   [字符串上的逻辑运算符](https://www.geeksforgeeks.org/g-fact-43-logical-operators-on-string-in-python/)
*   [使用%](http://geeksquiz.com/string-formatting-in-python-using/) 格式化字符串
*   [字符串模板类](https://www.geeksforgeeks.org/template-class-in-python/)
*   [劈开一根绳子](https://www.geeksforgeeks.org/how-to-split-a-string-in-cc-python-and-java/)
*   [Python 文档字符串](https://www.geeksforgeeks.org/python-docstrings/)
*   [切串](https://www.geeksforgeeks.org/string-slicing-python-check-string-can-become-empty-recursive-deletion/)
*   [查找字符串中所有重复的字符](https://www.geeksforgeeks.org/python-counter-find-duplicate-characters-string/)
*   [Python 中反串(5 种不同方式)](https://www.geeksforgeeks.org/reverse-string-python-5-different-ways/)
*   [Python 程序检查字符串是否回文](https://www.geeksforgeeks.org/python-program-check-string-palindrome-not/)

### 字符串常数

<figure class="table">

| 内置功能 | 描述 |
| --- | --- |
| [字符串. ascii _ 字母](https://www.geeksforgeeks.org/python-string-ascii_letters/) | ascii _ 小写和 ascii _ 大写常量的串联。 |
| [string . ascii _ 小写](https://www.geeksforgeeks.org/python-string-ascii_lowercase/) | 小写字母的串联 |
| 字符串. ascii_uppercase | 大写字母的串联 |
| [字符串数字](https://www.geeksforgeeks.org/python-string-digits/) | 字符串中的数字 |
| [字符串十六位数字](https://www.geeksforgeeks.org/python-string-hexdigits/) | 弦中的十六位数字 |
| 字符串。字母 | 字符串小写和大写的串联 |
| 字符串。小写 | 字符串必须包含小写字母。 |
| 字符串。八位数 | 字符串中的八位数 |
| 字符串。标点符号 | 带有标点符号的 ASCII 字符。 |
| 字符串。可打印 | 可打印的字符串 |
| [string . endcon()](https://www.geeksforgeeks.org/string-endswith-python/) | 如果字符串以给定的后缀结尾，则返回真，否则返回假 |
| [String.startswith()](https://www.geeksforgeeks.org/python-string-startswith/) | 如果字符串以给定的前缀开头，则返回真，否则返回假 |
| [String.isdigit（）](https://www.geeksforgeeks.org/python-string-isdigit-application/) | 如果字符串中的所有字符都是数字，则返回“真”，否则返回“假”。 |
| string . isalpha() | 如果字符串中的所有字符都是字母，则返回“真”，否则返回“假”。 |
| [string.isdecimal()](https://www.geeksforgeeks.org/python-string-isdecimal/) | 如果字符串中的所有字符都是十进制的，则返回 true。 |
| [str.format()](https://www.geeksforgeeks.org/python-format-function/) | Python3 中的字符串格式化方法之一，允许多次替换和值格式化。 |
| [字符串索引](https://www.geeksforgeeks.org/python-string-index-applications/) | 返回字符串中第一个出现的子字符串的位置 |
| 字符串。大写 | 字符串必须包含大写字母。 |
| [字符串.空白](https://www.geeksforgeeks.org/python-string-isspace-application/) | 包含所有被视为空白字符的字符串。 |
| [string.swapcase()](https://www.geeksforgeeks.org/python-string-swapcase/) | 方法将给定字符串的所有大写字符转换为小写字符，反之亦然，并返回它 |
| [替换()](https://www.geeksforgeeks.org/python-string-replace/) | 返回字符串的副本，其中一个子字符串的所有匹配项都被另一个子字符串替换。 |

</figure>

#### 不推荐使用的字符串函数

<figure class="table">

| 内置功能 | 描述 |
| --- | --- |
| [弦。是特殊的](https://www.geeksforgeeks.org/python-string-isdecimal/) | 如果字符串中的所有字符都是十进制的，则返回 true |
| [字符串。is lnum〔t1〕](https://www.geeksforgeeks.org/python-string-isalnum/) | 如果给定字符串中的所有字符都是字母数字，则返回 true。 |
| [字符串。ist tle〔t1〕](https://www.geeksforgeeks.org/python-string-istitle/) | 如果字符串是标题大小写的字符串，则返回 True |
| [弦分区](https://www.geeksforgeeks.org/string-partition-python/) | 在第一次出现分隔符时拆分字符串，并返回一个元组。 |
| [字符串。isi 识别符〔t1〕](https://www.geeksforgeeks.org/python-string-isidentifier/) | 检查字符串是否是有效的标识符。 |
| [String.len](https://www.geeksforgeeks.org/python-string-length-len/) | 返回字符串的长度。 |
| 字符串. rinex | 如果找到子字符串，则返回字符串中子字符串的最高索引。 |
| [弦。最大](https://www.geeksforgeeks.org/python-string-max/) | 返回字符串中最高的字母字符。 |
| [弦长](https://www.geeksforgeeks.org/python-string-min/) | 返回字符串中最小的字母字符。 |
| [弦线分裂线](https://www.geeksforgeeks.org/python-string-splitlines/) | 返回字符串中的行列表。 |
| [字符串.大写](https://www.geeksforgeeks.org/string-capitalize-python/) | 返回第一个字符大写的单词。 |
| [string . expandlabs](https://www.geeksforgeeks.org/python-expandtabs-method/) | 展开字符串中的制表符，用一个或多个空格替换它们 |
| [字符串.查找](https://www.geeksforgeeks.org/string-find-python/) | 返回子字符串的最低索引。 |
| [string.rfind](https://www.geeksforgeeks.org/python-string-rfind/) | 找到最高的指数。 |
| [细绳计数](https://www.geeksforgeeks.org/python-string-count/) | 返回字符串中子字符串 sub 的(非重叠)出现次数 |
| [降低弦](https://www.geeksforgeeks.org/python-string-lower/) | 返回 s 的副本，但大写字母转换为小写字母。 |
| [弦.分裂](https://www.geeksforgeeks.org/python-string-split/) | 如果缺少可选的第二个参数 sep 或无，则返回字符串的单词列表 |
| string . rslit() | 返回字符串 s 的单词列表，从头到尾扫描 s。 |
| [rpartition()](https://www.geeksforgeeks.org/python-string-rpartition/) | 方法将给定的字符串分成三部分 |
| string.splitfields | 仅与两个参数一起使用时，返回字符串的单词列表。 |
| [连接](https://www.geeksforgeeks.org/join-function-python/) | 将单词列表或元组与 sep 的中间出现连接起来。 |
| [string.strip()](https://www.geeksforgeeks.org/python-string-strip/) | 它返回字符串的副本，并删除前导和尾随空格 |
| [字符串。lsrip](https://www.geeksforgeeks.org/python-string-strip/) | 返回删除了前导空格的字符串副本。 |
| [string.rstrip](https://www.geeksforgeeks.org/python-string-rstrip/) | 返回字符串的副本，删除尾随空格。 |
| [字符串. swapcase](https://www.geeksforgeeks.org/python-string-swapcase/) | 将小写字母转换为大写字母，反之亦然。 |
| 字符串. translate | 使用表格翻译字符 |
| [弦上](https://www.geeksforgeeks.org/python-string-upper/) | 小写字母转换成大写字母。 |
| [弦.光](https://www.geeksforgeeks.org/string-rjust-ljust-python/) | 在给定宽度的字段中左对齐。 |
| [字符串。rust](https://www.geeksforgeeks.org/string-rjust-ljust-python/) | 在给定宽度的字段中右对齐。 |
| [string.center()](https://www.geeksforgeeks.org/string-center-python/) | 在给定宽度的字段中居中对齐。 |
| [字符串-zfill](https://www.geeksforgeeks.org/python-string-zfill/) | 用零数字填充左边的数字字符串，直到达到给定的宽度。 |
| [细绳.更换](https://www.geeksforgeeks.org/replace-in-python-to-replace-a-substring/) | 返回字符串 s 的副本，所有出现的子字符串旧的都被新的替换。 |
| [string.casefold()](https://www.geeksforgeeks.org/casefold-string-python/) | 以小写形式返回字符串，该字符串可用于无大小写比较。 |
| [字符串编码](https://www.geeksforgeeks.org/python-strings-encode-method/) | 将字符串编码为 Python 支持的任何编码。默认编码是 utf-8。 |
| [字串。maketrans](https://www.geeksforgeeks.org/python-maketrans-translate-functions/) | 返回可用于 str.translate()的转换表 |

</figure>

### [最近关于 Python 字符串的文章](https://www.geeksforgeeks.org/tag/python-string/)

https://youtu.be/mvDQuegHVXg

> **Python 字符串的更多视频:**
> [Python 字符串方法–第 2 部分](https://youtu.be/uWxLbPY9ewc)
> [Python 字符串方法–第 3 部分](https://youtu.be/ECnJ9AD6gHY)
> [字符串中的逻辑运算和拆分](https://youtu.be/m9iv9aM6Om8)

**Python 字符串的程序**

*   琴弦–[第一组](https://www.geeksforgeeks.org/interesting-facts-about-strings-in-python-set-1/)、[第二组](https://www.geeksforgeeks.org/interesting-facts-about-strings-in-python-set-2/)
*   弦法–[第 1 套](https://www.geeksforgeeks.org/string-methods-python-set-1/)、[第 2 套](https://www.geeksforgeeks.org/python-string-methods-set-2-len-count-center-ljust-rjust-isalpha-isalnum-isspace-join/)、[第 3 套](https://www.geeksforgeeks.org/python-string-methods-set-3-strip-lstrip-rstrip-min-max-maketrans-translate-relplace/)
*   [正则表达式(搜索、匹配和全部查找)](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/)
*   [Python 字符串标题方法](https://www.geeksforgeeks.org/title-in-python/)
*   [交换字符串中的逗号和圆点](https://www.geeksforgeeks.org/python-swap-commas-dots-string/)
*   [将字符串转换为列表的程序](https://www.geeksforgeeks.org/python-program-convert-string-list/)
*   [统计并显示字符串中的元音](https://www.geeksforgeeks.org/python-count-display-vowels-string/)
*   [检查密码有效性的 Python 程序](https://www.geeksforgeeks.org/python-program-check-validity-password/)
*   [Python 程序，使用给定字符串中的集合计算元音数量](https://www.geeksforgeeks.org/python-program-count-number-vowels-using-sets-given-string/)
*   [检查字符串中的网址](https://www.geeksforgeeks.org/python-check-url-string/)
*   [检查给定字符串中是否存在子字符串](https://www.geeksforgeeks.org/python-check-substring-present-given-string/)
*   [检查两个字符串是否是字谜](https://www.geeksforgeeks.org/python-sorted-check-two-strings-anagram-not/)
*   [将 Python 中的函数和字典映射到 ASCII 值的总和](https://www.geeksforgeeks.org/map-function-dictionary-python-sum-ascii-values/)
*   [Python 中映射函数和 Lambda 表达式替换字符](https://www.geeksforgeeks.org/map-function-lambda-expression-python-replace-characters/)
*   [Python 中最长公共子串的序列匹配器](https://www.geeksforgeeks.org/sequencematcher-in-python-for-longest-common-substring/)
*   [用全名打印姓名的首字母](https://www.geeksforgeeks.org/python-print-initials-name-last-name-full/)
*   [Python 中数据集最常出现的 k 个单词](https://www.geeksforgeeks.org/find-k-frequent-words-data-set-python/)
*   [从列表中找到输入字符串的所有相近匹配项](https://www.geeksforgeeks.org/python-find-close-matches-input-string-list/)
*   [检查二进制数中是否有 K 个连续的 1](https://www.geeksforgeeks.org/python-check-k-consecutive-1s-binary-number/)
*   [Python 中的 Lambda 和滤镜](https://www.geeksforgeeks.org/lambda-filter-python-examples/)
*   [Python 中包含不常见字符的串联字符串](https://www.geeksforgeeks.org/concatenated-string-uncommon-characters-python/)
*   [检查字符串的两半在 Python 中是否有相同的字符集](https://www.geeksforgeeks.org/check-halves-string-set-characters-python/)
*   [在 Python 中找到字符串中第一个重复的单词](https://www.geeksforgeeks.org/find-first-repeated-word-string-python-using-dictionary/)
*   [Python 中序列中重复次数第二多的单词](https://www.geeksforgeeks.org/second-repeated-word-sequence-python/)
*   [Python 中第 K 个非重复字符](https://www.geeksforgeeks.org/kth-non-repeating-character-python-using-list-comprehension-ordereddict/)
*   [在 Python 中反转给定字符串中的单词](https://www.geeksforgeeks.org/python-counter-find-duplicate-characters-string/)
*   [在 Python 中用逗号作为 1000 分隔符打印数字](https://www.geeksforgeeks.org/print-number-commas-1000-separators-python/)
*   [使用 pytrie 模块进行 Python 中的前缀匹配](Print number with commas as 1000 separators in Python)
*   [Python Regex 从字符串中提取最大数值](https://www.geeksforgeeks.org/python-regex-extract-maximum-numeric-value-string/)
*   [两组成对的完整琴弦](https://www.geeksforgeeks.org/python-set-pairs-complete-strings-two-sets/)
*   [删除给定句子中所有重复的单词](https://www.geeksforgeeks.org/python-remove-duplicates-words-given-sentence/)
*   [按升序排列句子的单词](https://www.geeksforgeeks.org/python-sort-words-sentence-ascending-order/)
*   [颠倒一个句子中的每个单词](https://www.geeksforgeeks.org/python-reverse-word-sentence/)
*   [Python 代码按字母顺序打印两个字符串的常用字符](https://www.geeksforgeeks.org/python-code-print-common-characters-two-strings-alphabetical-order/)
*   [Python 程序拆分并连接字符串](https://www.geeksforgeeks.org/python-program-split-join-string/)
*   [Python 代码，用于在单次遍历中将空格移动到字符串前面](https://www.geeksforgeeks.org/python-code-move-spaces-front-string-single-traversal/)
*   [Python 中的游程编码](https://www.geeksforgeeks.org/run-length-encoding-python/)
*   [在 Python 中删除给定字符串的所有重复项](https://www.geeksforgeeks.org/remove-duplicates-given-string-python/)
*   [在 Python 中增加字符的方法](https://www.geeksforgeeks.org/ways-increment-character-python/)
*   [使用 pytrie 模块进行 Python 中的前缀匹配](https://www.geeksforgeeks.org/prefix-matching-python-using-pytrie-module/)
*   [在 Python 中用逗号作为 1000 分隔符打印数字](https://www.geeksforgeeks.org/print-number-commas-1000-separators-python/)
*   [在 Python 中反转给定字符串中的单词](https://www.geeksforgeeks.org/reverse-words-given-string-python/)
*   [用 Python 执行一串代码](https://www.geeksforgeeks.org/execute-string-code-python/)
*   [Python 中的字符串切片，检查字符串是否可以通过递归删除变空](https://www.geeksforgeeks.org/string-slicing-python-check-string-can-become-empty-recursive-deletion/)
*   [Python 中转义字符的打印方式](https://www.geeksforgeeks.org/ways-print-escape-characters-python/)
*   [Python 中的字符串切片旋转字符串](https://www.geeksforgeeks.org/string-slicing-python-rotate-string/)
*   [统计字符串中某个单词的出现次数](https://www.geeksforgeeks.org/count-occurrences-of-a-word-in-string/)
*   [从 Python 中的数据集找到 k 个最常出现的单词](https://www.geeksforgeeks.org/find-k-frequent-words-data-set-python/)
*   [Python |用全名打印名字的首字母](https://www.geeksforgeeks.org/python-print-initials-name-last-name-full/)
*   [Python 中的 Zip 函数，改为新的字符集](https://www.geeksforgeeks.org/zip-function-python-change-new-character-set/)
*   [Python 字符串 isnumeric()及其应用](https://www.geeksforgeeks.org/python-string-isnumeric-application/)
*   [在 Python 中按照字典顺序对单词进行排序](https://www.geeksforgeeks.org/sort-words-lexicographical-order-python/)
*   [使用 Lambda 表达式求出现奇数次的次数，并减少函数](https://www.geeksforgeeks.org/python-find-number-occurring-odd-number-times-using-lambda-expression-reduce-function/)
*   [Python 字符串标题方法](https://www.geeksforgeeks.org/title-in-python/)
*   [按升序排列句子的单词](https://www.geeksforgeeks.org/python-sort-words-sentence-ascending-order/)
*   [将字符列表转换成字符串](https://www.geeksforgeeks.org/python-convert-list-characters-string/)
*   [Python groupby 方法删除所有连续的重复项](https://www.geeksforgeeks.org/python-groupby-method-remove-consecutive-duplicates/)
*   [Python groupby 方法删除所有连续的重复项](https://www.geeksforgeeks.org/python-groupby-method-remove-consecutive-duplicates/)
*   [从字符串中删除第 I 个字符的 Python 程序](https://www.geeksforgeeks.org/python-program-for-removing-i-th-character-from-a-string/)
*   [在 Python 中用数字替换字符串进行数据分析](https://www.geeksforgeeks.org/replacing-strings-with-numbers-in-python-for-data-analysis/)
*   [Python 中的格式化字符串文字(f 字符串)](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/)
*   [Python 文档字符串](https://www.geeksforgeeks.org/python-docstrings/)
*   [使用内置函数对给定字符串进行置换](https://www.geeksforgeeks.org/python-permutation-given-string-using-inbuilt-function/)
*   [在 Python 中找到一个字符串中每个单词的出现频率](https://www.geeksforgeeks.org/find-frequency-of-each-word-in-a-string-in-python/)
*   [接受包含所有元音的字符串的程序](https://www.geeksforgeeks.org/python-program-to-accept-the-strings-which-contains-all-vowels/)
*   [统计一对字符串中匹配字符的数量](https://www.geeksforgeeks.org/python-count-the-number-of-matching-characters-in-a-pair-of-string/)
*   [统计给定字符串中出现频率最高的所有前缀](https://www.geeksforgeeks.org/python-count-prefixes-given-string-greatest-frequency/)
*   [检查字符串是否包含任何特殊字符的程序](https://www.geeksforgeeks.org/python-program-check-string-contains-special-character/)
*   [生成随机字符串，直到生成给定的字符串](https://www.geeksforgeeks.org/python-program-match-string-random-strings-length/)
*   [不使用内置函数计算大小写字符的 Python 程序](https://www.geeksforgeeks.org/python-program-count-upper-lower-case-characters-without-using-inbuilt-functions/)