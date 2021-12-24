# Python |使用余弦相似度测量两个句子之间的相似度

> 原文:[https://www . geesforgeks . org/python-measure-两句话之间的相似度-使用-余弦-相似度/](https://www.geeksforgeeks.org/python-measure-similarity-between-two-sentences-using-cosine-similarity/)

**余弦相似度**是内积空间的两个非零向量之间相似度的度量，用于度量它们之间角度的余弦。
T3】相似度= (A.B) / (||A||。||B||) 其中 A 和 B 是向量。

本程序采用余弦相似性和 nltk 工具包模块。要执行此程序，nltk 必须安装在您的系统中。要安装 *nltk 模块*，请执行以下步骤–

```
1\. Open terminal(Linux).
2\. sudo pip3 install nltk
3\. python3
4\. import nltk
5\. nltk.download(‘all’)
```

**使用的功能:**

> **nltk.tokenize:** 用于标记化。标记化是将大量文本分成称为标记的较小部分的过程。`word_tokenize(X)`将给定的句子 X 拆分成单词，返回列表。
> 
> **nltk.corpus:** 在本程序中，用于获取停用词列表。停止词是一个常用词(如“the”、“a”、“an”、“in”)。

Below is the Python implementation –

```
# Program to measure the similarity between 
# two sentences using cosine similarity.
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize

# X = input("Enter first string: ").lower()
# Y = input("Enter second string: ").lower()
X ="I love horror movies"
Y ="Lights out is a horror movie"

# tokenization
X_list = word_tokenize(X) 
Y_list = word_tokenize(Y)

# sw contains the list of stopwords
sw = stopwords.words('english') 
l1 =[];l2 =[]

# remove stop words from the string
X_set = {w for w in X_list if not w in sw} 
Y_set = {w for w in Y_list if not w in sw}

# form a set containing keywords of both strings 
rvector = X_set.union(Y_set) 
for w in rvector:
    if w in X_set: l1.append(1) # create a vector
    else: l1.append(0)
    if w in Y_set: l2.append(1)
    else: l2.append(0)
c = 0

# cosine formula 
for i in range(len(rvector)):
        c+= l1[i]*l2[i]
cosine = c / float((sum(l1)*sum(l2))**0.5)
print("similarity: ", cosine)
```

**输出:**

```
similarity:  0.2886751345948129

```