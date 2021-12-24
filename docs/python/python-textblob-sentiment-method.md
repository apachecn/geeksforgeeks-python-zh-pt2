# Python | textblob . mooth()方法

> 原文:[https://www . geesforgeks . org/python-text blob-情操-方法/](https://www.geeksforgeeks.org/python-textblob-sentiment-method/)

借助`**TextBlob.sentiment()**`方法，我们可以通过`TextBlob.sentiment()`方法得到句子的情感。

> **语法:** `TextBlob.sentiment()`
> **返回:**返回情感元组。

**例 1 :**
在这个例子中，我们可以说通过使用`TextBlob.sentiment()`方法，我们能够获得一个句子的情感。

```py
# import TextBlob
from textblob import TextBlob

gfg = TextBlob("GFG is a good company and always value their employees.")

# using TextBlob.sentiment method
gfg = gfg.sentiment

print(gfg)
```

**输出:**

> 情感(极性=0.7，主观性=0.6000000000000001)

**例 2 :**

```py
# import TextBlob
from textblob import TextBlob

gfg = TextBlob("Sandeep Jain An IIT Roorkee alumnus and founder of GeeksforGeeks. He loves to solve programming problems in most efficient ways.")

# using TextBlob.sentiment method
gfg = gfg.sentiment

print(gfg)
```

**输出:**

> 情感(极性=0.5，主观性=0.5)