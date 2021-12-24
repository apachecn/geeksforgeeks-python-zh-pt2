# Python |使用文本块标记文本

> 原文:[https://www . geesforgeks . org/python-token ize-text-using-text blob/](https://www.geeksforgeeks.org/python-tokenize-text-using-textblob/)

`**TextBlob**`模块是一个 Python 库，提供了一个简单的 API 来访问其方法和执行基本的 NLP 任务。它建立在 NLTK 模块的顶部。

在终端中使用以下命令安装 TextBlob:

```py
pip install -U textblob
python -m textblob.download_corpora

```

这将安装 TextBlob 并下载必要的 NLTK 语料库。由于需要下载大量的标记器、分块器、其他算法和所有的语料库，上述安装将花费相当长的时间。

一些经常使用的术语是:

*   **语料库**–正文，单数。语料库是这个的复数。
*   **词汇**–单词及其含义。
*   **标记**–每一个“实体”都是基于规则分割的一部分。例如，当一个句子被“标记化”成单词时，每个单词都是一个标记。如果你把一个段落中的句子标记出来，每个句子也可以是一个标记。

**所以基本上标记化包括从正文中拆分句子和单词。**

```py
# from textblob lib. import TextBlob method
from textblob import TextBlob

text = ("Natural language processing (NLP) is a field " + 
       "of computer science, artificial intelligence " + 
       "and computational linguistics concerned with " +  
       "the interactions between computers and human " +  
       "(natural) languages, and, in particular, " +  
       "concerned with programming computers to " + 
       "fruitfully process large natural language " +  
       "corpora. Challenges in natural language " +  
       "processing frequently involve natural " + 
       "language understanding, natural language" +  
       "generation frequently from formal, machine" +  
       "-readable logical forms), connecting language " +  
       "and machine perception, managing human-" + 
       "computer dialog systems, or some combination " +  
       "thereof.")

# create a TextBlob object
blob_object = TextBlob(text)

# tokenize paragraph into words.
print(" Word Tokenize :\n", blob_object.words)

# tokenize paragraph into sentences.
print("\n Sentence Tokenize :\n", blob_object.sentences)
```

**输出:**

> word token ize:
> [“natural”，“language”，“processing”，“NLP”，“is”，“a”，“field”，“of”，“computer”，“science”，“artificial”，“intelligence”，“and”，“computational”，“with”，“the”，“interactions”，“interactions”，“computers”，“and”，“in”，“specific”，“with”，“programming”，“computers”，“to”，“foundly”，“process”，“large”，“natural”，“language”，“Challenges”，“in”，“Natural”，“processing”，“频繁涉及”，“Natural”，“language”，“languagegeneration”，“frequency”，“from”，“forms”，“机器可读”，“logical
> 
> 句子 Tokenize :
> 【句子】(“自然语言处理(NLP)是计算机科学、人工智能和计算语言学的一个领域，涉及计算机和人类(自然)语言之间的交互，特别是涉及对计算机进行编程以有效处理大型自然语言语料库。”)、句子(“自然语言处理中的挑战经常涉及自然语言理解、自然语言经常从形式的、机器可读的逻辑形式生成)、连接语言和机器感知、管理人机对话系统或它们的某种组合。”)]