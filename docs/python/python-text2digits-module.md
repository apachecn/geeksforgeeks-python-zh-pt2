# Python 文本 2 数字模块

> 原文:[https://www.geeksforgeeks.org/python-text2digits-module/](https://www.geeksforgeeks.org/python-text2digits-module/)

一个 **text2digits** 模块是 python 的库，它帮助你将文本数字转换成字符串中的数字。您可以在 Alexa/Lex 操作中发现这一点很有用，将音频转换为文本，并且必须将文本转换为数字。

#### 安装库

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```
pip install text2digits
```

**例:**

```
# Importing text2digits function  

# From text2digits Library  

from text2digits import text2digits

# we have to create a object of this function

a = text2digits.Text2Digits()

from text2digits import text2digits
a = text2digits.Text2Digits()

ans = a.convert("twenty ten and thirty six")
print(ans)

ans = a.convert("I was born in nineteen ninety nine")
print(ans)

ans = a.convert("I am twenty ")
print(ans)

ans = a.convert("one thousand and six hundred and sixty six")
print(ans)

ans = a.convert("I was born in nineteen eighty eight and am  thirty two years old !")
print(ans)

ans = a.convert("sixty billion forty million twenty thousand four hundred six")
print(ans)

ans = a.convert("I am thirty six years old with a child who is four.")
print(ans)

ans = a.convert("one is not divisible by zero")
print(ans)

ans = a.convert("Sixteen and seven" )
print(ans)

ans = a.convert("one two three four five six seven eight nine")
print(ans)
type(ans)
```

**输出:**

```
2010 and 36
I was born in 19 ninetynine
I am 20 
1666
I was born in 1988 and am  32 years old !
60040020406
I am 36 years old with a child who is 4.
1 is not divisible by 0
16 and 7
123456789
str
```

**注意:** **文本 2 数字**总是以字符串作为输入，否则会引发**语法错误**。