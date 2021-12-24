# python–删除重音模块

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-remove accents-module/

**移除重音**模块是 python 库，它可以帮助你移除给定字符串中的所有重音。最常见的口音是*锐音(é)* 、*庄重(è)* 、*扬抑音(β、μ或)*、 *umlaut 和 dieresis (ü或)*。重音符号通常出现在字符上方。
它可以广泛用于自然语言处理，通过去除给定文本中的所有重音来过滤掉数据。

**安装库:**

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

> pip 安装删除程序重音

**remove _ 口音:**将字符串中的字符去掉所有口音后返回字符串。

**示例:**

```py
# Importing removeaccents function  
# From removeaccents Library  
from removeaccents import removeaccents

str_input ="Ît löökèd cóol ând câsüâl, büt nôt prôvôcâtïvê ."
str_output = removeaccents.remove_accents(str_input)
print(str_output)

str_input ="För môrê àrticlés vîsit GééksförGèèks ."
str_output = removeaccents.remove_accents(str_input)
print(str_output)

str_input ="https://äüth.gèéksforgëëks.ôrg / usër / vâsü_gûptâ/àrtîclés ."
str_output = removeaccents.remove_accents(str_input)
print(str_output)
```

**输出:**

```py
It looked cool and casual, but not provocative .

For more articles visit GeeksforGeeks .

https://auth.geeksforgeeks.org/user/vasu_gupta/articles .

```

**参考:**T2】pypy.org