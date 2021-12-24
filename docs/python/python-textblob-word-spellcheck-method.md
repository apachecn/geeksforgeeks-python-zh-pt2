# Python | TextBlob。Word .拼写检查()方法

> 原文:[https://www . geesforgeks . org/python-text blob-word-spell check-method/](https://www.geeksforgeeks.org/python-textblob-word-spellcheck-method/)

借助`**TextBlob.Word.spellcheck()**`方法，我们可以使用`TextBlob.Word.spellcheck()`方法检查该单词是否有拼写错误。

> **语法:** `TextBlob.Word.spellcheck()`
> **返回:**以正确的准确性返回单词。

**示例#1 :**
在这个示例中，我们可以说通过使用`TextBlob.Word.spellcheck()`方法，我们能够获得单词 weather 的准确性，它是否正确。

```py
# import Word
from textblob import Word

gfg = Word("Facility")

# using Word.spellcheck() method
print(gfg.spellcheck())
```

**输出:**

> [(“设施”，1.0)]

**例 2 :**

```py
# import Word
from textblob import Word

gfg = Word("Prediction")

# using Word.spellcheck() method
print(gfg.spellcheck())
```

**输出:**

> [(“预测”，1.0)]