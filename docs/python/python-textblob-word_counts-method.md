# Python | TextBlob.word_counts()方法

> 原文:[https://www . geesforgeks . org/python-textblob-word _ counts-method/](https://www.geeksforgeeks.org/python-textblob-word_counts-method/)

借助`**TextBlob.word_counts()**`方法，我们可以利用`TextBlob.word_counts()`方法得到句子中某个特定单词的字数。

> **语法:** `TextBlob.word_counts()`
> **返回:**返回一个句子的字数。

**示例#1 :**
在这个示例中，我们可以说通过使用`TextBlob.word_counts()`方法，我们能够获得一个句子中的字数。

```py
# import TextBlob
from textblob import TextBlob

gfg = TextBlob("I am confused sometime, sometime I messed up things.")

# using TextBlob.word_counts() method
gfg = gfg.word_counts['sometime']

print(gfg)
```

**输出:**

> Two

**例 2 :**

```py
# import TextBlob
from textblob import TextBlob

gfg = TextBlob("My name is Khan khan KhaN.")

# using TextBlob.word_counts() method
gfg = gfg.word_counts['khan']

print(gfg)
```

**输出:**

> three