# Python | TextBlob.correct()方法

> 原文:[https://www . geesforgeks . org/python-text blob-correct-method/](https://www.geeksforgeeks.org/python-textblob-correct-method/)

借助 **TextBlob.correct()** 方法，使用 TextBlob.correct()方法，如果任何句子有拼写错误，我们就可以得到纠正的单词。

> **语法:**textblob . correct()
> T3】Return:返回正确的句子，没有拼写错误。

**示例#1 :**
在这个示例中，我们可以说通过使用 TextBlob.correct()方法，我们能够在没有任何拼写错误的情况下获得正确的句子。

## 蟒蛇 3

```
# import TextBlob
from textblob import TextBlob

gfg = TextBlob("GFG is a good compny and alays valule ttheir employes.")

# using TextBlob.correct() method
gfg = gfg.correct()

print(gfg)
```

**输出:**

```
GFG is a good company and always value their employed. 

```

**例 2:**

## 蟒蛇 3

```
# import TextBlob
from textblob import TextBlob

gfg = TextBlob("I amm goodd at speling mstake.")

# using TextBlob.correct() method
gfg = gfg.correct()

print(gfg)
```

**输出:**

```
I am good at spelling mistake. 

```