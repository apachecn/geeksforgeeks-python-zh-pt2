# Python |在字符串中交换逗号和圆点

> 原文:[https://www . geesforgeks . org/python-swap-逗号-点-字符串/](https://www.geeksforgeeks.org/python-swap-commas-dots-string/)

问题很简单。给定一个字符串，我们需要用点替换所有的逗号，用逗号替换所有的点。这可以通过两种流行的方式来实现。
示例:

```py
Input : 14, 625, 498.002
Output : 14.625.498, 002 
```

**使用 maketrans 和 translate()**

**maketrans:** 这个静态方法返回一个可用于 *str.translate()* 的翻译表。这将构建一个转换表，它是整数或字符到整数、字符串或无的映射。
**translate:** 这将返回一个字符串副本，其中可选参数中出现的所有字符都将被删除，剩余的字符将通过 maketrans 表映射。
更多参考请访问 [Python 字符串方法](https://www.geeksforgeeks.org/python-string-methods-set-3-strip-lstrip-rstrip-min-max-maketrans-translate-relplace/)。

## 蟒蛇 3

```py
# Python code to replace, with . and vice-versa
def Replace(str1):
    maketrans = str1.maketrans
    final = str1.translate(maketrans(',.', '.,', ' '))
    return final.replace(',', ", ")

# Driving Code
string = "14, 625, 498.002"
print(Replace(string))
```

**输出:**

```py
14.625.498, 002
```

**使用 replace()**

这更像是一种逻辑方法，我们交换符号，考虑第三个变量。replace 方法也可以用来替换字符串中的方法。我们可以将“”转换为一个符号，然后再转换“”。to " "和符号 to " "。。更多参考请访问 [Python 字符串方法](https://www.geeksforgeeks.org/python-string-methods-set-3-strip-lstrip-rstrip-min-max-maketrans-translate-relplace/)。
例:

## 蟒蛇 3

```py
def Replace(str1):
    str1 = str1.replace(', ', 'third')
    str1 = str1.replace('.', ', ')
    str1 = str1.replace('third', '.')
    return str1

string = "14, 625, 498.002"
print(Replace(string))
```

**输出:**

```py
14.625.498, 002
```