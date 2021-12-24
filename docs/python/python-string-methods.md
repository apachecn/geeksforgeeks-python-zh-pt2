# Python 字符串方法

> 原文:[https://www.geeksforgeeks.org/python-string-methods/](https://www.geeksforgeeks.org/python-string-methods/)

[**Python 字符串**](https://www.geeksforgeeks.org/python-strings/) 是包含在引号中的 Unicode 字符序列。在本文中，我们将讨论内置函数，即 Python 提供的对字符串进行操作的函数。

**注意:**每个字符串方法都不会改变原来的字符串，而是返回一个属性改变的新字符串。

## 字符串的大小写改变

以下函数用于改变字符串的大小写。

*   [**lower():**](https://www.geeksforgeeks.org/python-string-lower/) 将字符串中的所有大写字符转换为小写字符
*   [**upper():**](https://www.geeksforgeeks.org/python-string-upper/) 将字符串中的所有小写字符转换为大写
*   [**标题():**](https://www.geeksforgeeks.org/title-in-python/) 将字符串转换为标题大小写

**示例:**改变 Python 字符串的大小写。

## 蟒蛇 3

```
# Python3 program to show the
# working of upper() function
text = 'geeKs For geEkS'

# upper() function to convert
# string to upper_case
print("\nConverted String:")
print(text.upper())

# lower() function to convert
# string to upper_case
print("\nConverted String:")
print(text.lower())

# rpartition breaks the string
print("\nConverted String:")
print(text.title())

# original string never changes
print("\nOriginal String")
print(text)
```

**Output**

```
Converted String:
GEEKS FOR GEEKS

Converted String:
geeks for geeks

Converted String:
Geeks For Geeks

Original String
geeKs For geEkS
```

## Python 字符串方法表

<figure class="table">

| 函数名 | 描述 |
| --- | --- |
| [大写()](https://www.geeksforgeeks.org/string-capitalize-python/) | 将字符串的第一个字符转换为大写字母 |
| [casefold()](https://www.geeksforgeeks.org/casefold-string-python/) | 实现无大小写的字符串匹配 |
| [中心()](https://www.geeksforgeeks.org/string-center-python/) | 用指定的字符填充字符串。 |
| [计数()](https://www.geeksforgeeks.org/python-string-count/) | 返回子字符串在字符串中出现的次数。 |
| [编码()](https://www.geeksforgeeks.org/python-strings-encode-method/) | 用指定的编码方案编码字符串 |
| [end with()](https://www.geeksforgeeks.org/string-endswith-python/) | 如果字符串以给定的后缀结尾，则返回“真” |
| [扩展选项卡()](https://www.geeksforgeeks.org/python-expandtabs-method/) | 指定字符串中要用“\t”符号替换的空间量 |
| [find()](https://www.geeksforgeeks.org/python-string-find/) | 如果找到子字符串，则返回它的最低索引 |
| [格式()](https://www.geeksforgeeks.org/python-format-function/) | 格式化字符串以将其打印到控制台 |
| [format_map()](https://www.geeksforgeeks.org/python-string-format_map/) | 使用字典格式化字符串中的指定值 |
| [指数()](https://www.geeksforgeeks.org/python-string-index-applications/) | 返回子字符串在字符串中第一次出现的位置 |
| [【is lnum()](https://www.geeksforgeeks.org/python-string-isalnum/) | 检查给定字符串中的所有字符是否都是字母数字 |
| [异α（）](https://www.geeksforgeeks.org/python-string-isalpha-application/) | 如果字符串中的所有字符都是字母，则返回“真” |
| [isdiction()](https://www.geeksforgeeks.org/python-string-isdecimal/) | 如果字符串中的所有字符都是十进制的，则返回 true |
| [isdigital()](https://www.geeksforgeeks.org/python-string-isdigit-application/) | 如果字符串中的所有字符都是数字，则返回“真” |
| [isi identifier()](https://www.geeksforgeeks.org/python-string-isidentifier/) | 检查字符串是否是有效的标识符 |
| [岛电()](https://www.geeksforgeeks.org/python-string-islower-method/) | 检查字符串中的所有字符是否都是小写 |
| [isnumeric()](https://www.geeksforgeeks.org/python-string-isnumeric-application/) | 如果字符串中的所有字符都是数字字符，则返回“真” |
| [可打印（）](https://www.geeksforgeeks.org/isprintable-python-application/) | 如果字符串中的所有字符都是可打印的或字符串为空，则返回“真” |
| [这种空间()](https://www.geeksforgeeks.org/python-string-isspace-application/) | 如果字符串中的所有字符都是空白字符，则返回“真” |
| [标题（）](https://www.geeksforgeeks.org/python-string-istitle/) | 如果字符串是标题大小写的字符串，则返回“真” |
| [isupper()](https://www.geeksforgeeks.org/python-string-isupper-method/) | 检查字符串中的所有字符是否都是大写 |
| [join()](https://www.geeksforgeeks.org/join-function-python/) | 返回串联字符串 |
| 光源() | 根据指定的宽度向左对齐字符串 |
| [下降()](https://www.geeksforgeeks.org/python-string-lower/) | 将字符串中的所有大写字符转换为小写字符 |
| [【lsrip()](https://www.geeksforgeeks.org/python-string-lstrip-method/) | 返回去掉前导字符的字符串 |
| maketrans() | 返回一个翻译表 |
| [分区()](https://www.geeksforgeeks.org/string-partition-python/) | 在分隔符第一次出现时拆分字符串 |
| [替换()](https://www.geeksforgeeks.org/python-string-replace/) | 用另一个子串替换一个子串的所有出现 |
| [rfnd()](https://www.geeksforgeeks.org/python-string-rfind/) | 返回子字符串的最高索引 |
| [rinex()](https://www.geeksforgeeks.org/string-rindex-python/) | 返回字符串中子字符串的最高索引 |
| rjust（） | 根据指定的宽度向右对齐字符串 |
| [rpartition()](https://www.geeksforgeeks.org/python-string-rpartition/) | 将给定的字符串分成三部分 |
| [rslit()](https://www.geeksforgeeks.org/python-string-rsplit/) | 通过指定的分隔符从右侧拆分字符串 |
| [rstrip()](https://www.geeksforgeeks.org/python-string-rstrip/) | 删除尾随字符 |
| [分割线()](https://www.geeksforgeeks.org/python-string-splitlines/) | 在线边界处拆分线 |
| [开头为()](https://www.geeksforgeeks.org/python-string-startswith/) | 如果字符串以给定前缀开头，则返回“真” |
| [条状()](https://www.geeksforgeeks.org/python-string-strip/) | 返回包含前导和尾随字符的字符串 |
| [掉期()](https://www.geeksforgeeks.org/python-string-swapcase/) | 将所有大写字符转换为小写字符，反之亦然 |
| [标题（）](https://www.geeksforgeeks.org/title-in-python/) | 将字符串转换为标题大小写 |
| [平移()](https://www.geeksforgeeks.org/python-string-translate/) | 根据给定的转换映射修改字符串 |
| [上()](https://www.geeksforgeeks.org/python-string-upper/) | 将字符串中的所有小写字符转换为大写字符 |
| [zfzl()](https://www.geeksforgeeks.org/python-string-zfill/) | 返回字符串的副本，在字符串的左侧填充“0”个字符 |

</figure>

**注意:**关于 Python 字符串的更多信息，请参考 [Python 字符串教程](https://www.geeksforgeeks.org/python-strings/)。