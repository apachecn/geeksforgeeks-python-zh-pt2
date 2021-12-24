# Python |使用 spaCy 的单词相似度

> 原文:[https://www . geesforgeks . org/python-word-相似性-use-spacy/](https://www.geeksforgeeks.org/python-word-similarity-using-spacy/)

**单词相似度**是一个 0 到 1 之间的数字，它告诉我们两个单词在语义上有多接近。这是通过在向量空间中找到单词向量之间的相似性来完成的。spaCy 是当今广泛使用的最快的 NLP 库之一，它为这项任务提供了一种简单的方法。

**spaCy 的 Model–**
spaCy 支持两种查找单词相似度的方法:使用上下文敏感张量和使用单词向量。下面是下载这些模型的代码。

```py
# Downloading the small model containing tensors.
python -m spacy download en_core_web_sm

# Downloading over 1 million word vectors.
python -m spacy download en_core_web_lg

```

下面是查找单词相似度的代码，可以扩展到句子和文档。

```py
import spacy

nlp = spacy.load('en_core_web_md')

print("Enter two space-separated words")
words = input()

tokens = nlp(words)

for token in tokens:
    # Printing the following attributes of each token.
    # text: the word string, has_vector: if it contains
    # a vector representation in the model, 
    # vector_norm: the algebraic norm of the vector,
    # is_oov: if the word is out of vocabulary.
    print(token.text, token.has_vector, token.vector_norm, token.is_oov)

token1, token2 = tokens[0], tokens[1]

print("Similarity:", token1.similarity(token2))
```

**输出:**

```py
cat True 6.6808186 False
dog True 7.0336733 False
Similarity: 0.80168545

```

“en_core_web_md”模型为“狗”和“猫”生成 300*1 维的向量。也可以使用更大的模型“en_vectors_web_lg”，它为相同的两个单词产生更大维度的向量。

**使用自定义语言模型–**
通过简单地切换语言模型，我们可以发现拉丁语、法语或德语文档之间的相似性。spaCy 目前总共支持 49 种语言。spaCy 还允许用户根据需要固定单词的单词向量。下面是一个例子。

```py
import spacy
import numpy as np
from spacy.vocab import Vocab

nlp = spacy.load('en_core_web_md')
new_word = 'bucrest'

print('Before custom setting')
print(vocab.get_vector('bucrest'))

custom_vector = np.random.uniform(-1, 1, (300, ))

vocab.set_vector(new_word, custom_vector)

print('After custom setting')
print(vocab.get_vector('bucrest'))
```

**输出:**

```py
Before custom setting
array([0., 0., 0., 0., 0., 0., 0., 0., --- ])

After custom setting
array([ 0.68106073,  0.6037007,  0.9526876, -0.25600302, -0.24049562, --- ])

```