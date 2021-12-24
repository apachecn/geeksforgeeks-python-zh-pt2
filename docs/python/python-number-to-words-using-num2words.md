# Python |使用 num2words 将数字转换为单词

> 原文:[https://www . geesforgeks . org/python-number-to-words-use-num 2 words/](https://www.geeksforgeeks.org/python-number-to-words-using-num2words/)

Python 中的 num2words 模块，它将数字(如 34)转换为单词(如 34)。此外，该库支持多种语言。在本文中，我们将看到如何使用`num2words` 模块将数字转换为单词。

**安装**T3】使用画中画可以轻松安装`num2words`。

```py
pip install num2words

```

考虑以下从 20 个新闻组(一个流行的 NLP 数据库)中提取的不同文件的两个摘录。有效地预处理 20 个新闻组仍然是一个令人感兴趣的问题。

> 在文章中，马丁·普雷斯顿写道:为什么不使用 PD C 库来读写 TIFF 文件呢？我花了整整 **20** 分钟才开始在你自己的应用中使用它们。
> ISCIS VIII 是来自大约 20 个国家的计算机科学家和工程师齐聚一堂的一系列会议中的第八次。今年的会议将在美丽的地中海度假城市安塔利亚举行，该地区有丰富的自然和历史遗迹。

在上面两个摘录中，可以观察到数字“20”以数字和字母的形式出现。简单地遵循预处理步骤(包括标记化、引理化等)将无法将“20”和“20”映射到同一个词干，这对于上下文很重要。幸运的是，我们有内置的库，`num2words`可以在一行中解决这个问题。

以下是该工具的使用示例。

```py
from num2words import num2words

# Most common usage.
print(num2words(36))

# Other variants, according to the type of article.
print(num2words(36, to = 'ordinal'))
print(num2words(36, to = 'ordinal_num'))
print(num2words(36, to = 'year'))
print(num2words(36, to = 'currency'))

# Language Support.
print(num2words(36, lang ='es'))
```

**输出:**

```py
thirty-six
thirty-sixth
36th
zero euro, thirty-six cents
treinta y seis

```

因此，在预处理步骤中，可以将所有数值转换为单词，以便在后续阶段中获得更好的准确性。

**参考文献:**T2】https://pypi.org/project/num2words/