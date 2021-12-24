# Python |使用 TextBlob 的词性标注

> 原文:[https://www . geesforgeks . org/python-词性标注-使用-textblob/](https://www.geeksforgeeks.org/python-part-of-speech-tagging-using-textblob/)

`TextBlob` 模块用于构建文本分析程序。文本块模块更强大的方面之一是词性标注。

安装文本 Blob 运行以下命令:

```py
$ pip install -U textblob
$ python -m textblob.download_corpora

```

这将安装 TextBlob 并下载必要的 NLTK 语料库。

由于需要下载大量的标记器、分块器、其他算法和所有的语料库，上述安装将花费相当长的时间。

> 让我们找出一些快速词汇:
> 
> **语料库:**正文，单数。语料库是这个的复数。
> **词汇:**单词及其含义。
> **令牌:**每一个“实体”都是基于规则分割的一部分。

在语料库语言学中，词性标注(词性标注或词性标注或 POST)，也称为**语法标注**或**词类消歧。**

```py
Input: Everything is all about money.
Output: [('Everything', 'NN'), ('is', 'VBZ'), 
              ('all', 'DT'), ('about', 'IN'), 
                             ('money', 'NN')] 

```

以下是标签列表、它们的含义以及一些示例:

```py
CC coordinating conjunction
CD cardinal digit
DT determiner
EX existential there (like: “there is” … think of it like “there exists”)
FW foreign word
IN preposition/subordinating conjunction
JJ adjective ‘big’
JJR adjective, comparative ‘bigger’
JJS adjective, superlative ‘biggest’
LS list marker 1)
MD modal could, will
NN noun, singular ‘desk’
NNS noun plural ‘desks’
NNP proper noun, singular ‘Harrison’
NNPS proper noun, plural ‘Americans’
PDT predeterminer ‘all the kids’
POS possessive ending parent‘s
PRP personal pronoun I, he, she
PRP$ possessive pronoun my, his, hers
RB adverb very, silently,
RBR adverb, comparative better
RBS adverb, superlative best
RP particle give up
TO to go ‘to‘ the store.
UH interjection errrrrrrrm
VB verb, base form take
VBD verb, past tense took
VBG verb, gerund/present participle taking
VBN verb, past participle taken
VBP verb, sing. present, non-3d take
VBZ verb, 3rd person sing. present takes
WDT wh-determiner which
WP wh-pronoun who, what
WP$ possessive wh-pronoun whose
WRB wh-abverb where, when

```

```py
# from textblob lib import TextBlob method
from textblob import TextBlob

text = ("Sukanya, Rajib and Naba are my good friends. " +
    "Sukanya is getting married next year. " +
    "Marriage is a big step in one’s life." +
    "It is both exciting and frightening. " + 
    "But friendship is a sacred bond between people." +
    "It is a special kind of love between us. " +
    "Many of you must have tried searching for a friend "+ 
    "but never found the right one.")

# create a textblob object
blob_object = TextBlob(text)

# Part-of-speech tags can be accessed 
# through the tags property of blob object.'

# print word with pos tag.
print(blob_object.tags)
```

**输出:**

```py
[('Sukanya', 'NNP'),
 ('Rajib', 'NNP'),
 ('and', 'CC'),
 ('Naba', 'NNP'),
 ('are', 'VBP'),
 ('my', 'PRP{content}apos;),
 ('good', 'JJ'),
 ('friends', 'NNS'),
 ('Sukanya', 'NNP'),
 ('is', 'VBZ'),
 ('getting', 'VBG'),
 ('married', 'VBN'),
 ('next', 'JJ'),
 ('year', 'NN'),
 ('Marriage', 'NN'),
 ('is', 'VBZ'),
 ('a', 'DT'),
 ('big', 'JJ'),
 ('step', 'NN'),
 ('in', 'IN'),
 ('one', 'CD'),
 ('’', 'NN'),
 ('s', 'NN'),
 ('life.It', 'NN'),
 ('is', 'VBZ'),
 ('both', 'DT'),
 ('exciting', 'VBG'),
 ('and', 'CC'),
 ('frightening', 'NN'),
 ('But', 'CC'),
 ('friendship', 'NN'),
 ('is', 'VBZ'),
 ('a', 'DT'),
 ('sacred', 'JJ'),
 ('bond', 'NN'),
 ('between', 'IN'),
 ('people.It', 'NN'),
 ('is', 'VBZ'),
 ('a', 'DT'),
 ('special', 'JJ'),
 ('kind', 'NN'),
 ('of', 'IN'),
 ('love', 'NN'),
 ('between', 'IN'),
 ('us', 'PRP'),
 ('Many', 'JJ'),
 ('of', 'IN'),
 ('you', 'PRP'),
 ('must', 'MD'),
 ('have', 'VB'),
 ('tried', 'VBN'),
 ('searching', 'VBG'),
 ('for', 'IN'),
 ('a', 'DT'),
 ('friend', 'NN'),
 ('but', 'CC'),
 ('never', 'RB'),
 ('found', 'VBD'),
 ('the', 'DT'),
 ('right', 'JJ'),
 ('one', 'NN')]

```

基本上，词性标注的目标是将语言(主要是语法)信息分配给子句子单位。这种单位被称为记号，在大多数情况下，对应于单词和符号(例如标点符号)。