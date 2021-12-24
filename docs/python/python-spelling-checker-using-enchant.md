# Python–使用附魔的拼写检查器

> 原文:[https://www . geesforgeks . org/python-拼写检查-使用-附魔/](https://www.geeksforgeeks.org/python-spelling-checker-using-enchant/)

附魔是 Python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

附魔也可以用来检查单词的拼写。如果传递的单词出现在语言词典中，check()方法返回 True，否则返回 False。check()方法的这一功能可用于拼写检查单词。

建议()方法用于建议拼写错误的单词的正确拼写。

## 蟒蛇 3

```
# import the enchant module
import enchant

# create dictionary for the language
# in use(en_US here)
dict = enchant.Dict("en_US")

# list of words
words = ["cmputr", "watr", "study", "wrte"]

# find those words that may be misspelled
misspelled =[]
for word in words:
    if dict.check(word) == False:
        misspelled.append(word)
print("The misspelled words are : " + str(misspelled))

# suggest the correct spelling of
# the misspelled words
for word in misspelled:
    print("Suggestion for " + word + " : " + str(dict.suggest(word)))
```

**输出:**

```
The misspelled words are : ['cmputr', 'watr', 'wrte']
Suggestion for cmputr : ['computer']
Suggestion for watr : ['wart', 'watt', 'wat', 'war', 'water', 'wat r']
Suggestion for wrte : ['rte', 'write', 'wrote', 'wert', 'wite', 'w rte']
```