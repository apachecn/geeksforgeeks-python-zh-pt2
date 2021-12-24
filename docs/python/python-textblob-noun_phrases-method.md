# Python | TextBlob .名词 _ 短语()方法

> 原文:[https://www . geesforgeks . org/python-text blob-名词 _ 短语-方法/](https://www.geeksforgeeks.org/python-textblob-noun_phrases-method/)

借助`**TextBlob.noun_phrases()**`方法，我们可以利用`TextBlob.noun_phrases()`方法得到句子的名词短语。

> **语法:** `TextBlob.noun_phrases()`
> **返回:**返回名词值列表。

**示例#1 :**
在这个示例中，我们可以说通过使用`TextBlob.noun_phrases()`方法，我们能够获得名词单词的列表。

```
# import TextBlob
from textblob import TextBlob

gfg = TextBlob("Python is a high-level language.")

# using TextBlob.noun_phrases method
gfg = gfg.noun_phrases

print(gfg)
```

**输出:**

> [“python”，“高级语言”

**例 2 :**

```
# import TextBlob
from textblob import TextBlob

gfg = TextBlob("Sandeep Jain An IIT Roorkee alumnus and founder of GeeksforGeeks. He loves to solve programming problems in most efficient ways.")

# using TextBlob.noun_phrases method
gfg = gfg.noun_phrases

print(gfg)
```

**输出:**

> ['sandeep jain '，' iit roorkee '，' geeksforgeeks '，'高效方法']