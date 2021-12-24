# TF–二元模型&三元模型

的 IDF

> 原文:[https://www.geeksforgeeks.org/tf-idf-for-bigrams-trigrams/](https://www.geeksforgeeks.org/tf-idf-for-bigrams-trigrams/)

自然语言处理中的 TF-IDF 代表**术语频率–逆文档频率**。这是自然语言处理中的一个非常热门的话题，通常涉及人类语言。在任何文本处理过程中，清理文本(预处理)至关重要。此外，清理后的数据需要转换成数字格式，其中每个单词由矩阵(单词向量)表示。这也称为**嵌入单词**
术语频率(TF) =(文档中某个术语的频率)/(文档中的术语总数)
逆文档频率(IDF) =(文档总数)/(带有术语 t 的文档数)
**TF。IDF = (TF)。(IDF)**

**Bigrams:** Bigram 是一个句子中连续的 2 个单词。例如**“男孩在踢足球”**。这里的大人物是:

```
The boy
Boy is
Is playing
Playing football

```

**三元组:**三元组是一个句子中连续的 3 个单词。对于上面的例子，三元模型是:

```
The boy is
Boy is playing
Is playing football
```

从上面的二元模型和三元模型来看，一些是相关的，而另一些则被丢弃，对进一步的处理没有价值。
假设我们想从一份文件中找到成为“数据科学家”所需的技能。在这里，如果我们只考虑单字，那么单字就不能恰当地表达细节。如果我们有一个像“机器学习开发者”这样的词，那么提取的词应该是“机器学习”或“机器学习开发者”。简单的“机器”、“学习”或“开发者”这些词不会给出预期的结果。

**代码–图解三元组的详细解释**

```
# Importing libraries
import nltk
import re
from sklearn.feature_extraction.text import CountVectorizer, TfidfVectorizer
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
import pandas as pd

# Input the file 
txt1 = []
with open('C:\\Users\\DELL\\Desktop\\MachineLearning1.txt') as file:
    txt1 = file.readlines()

# Preprocessing
def remove_string_special_characters(s):

    # removes special characters with ' '
    stripped = re.sub('[^a-zA-z\s]', '', s)
    stripped = re.sub('_', '', stripped)

    # Change any white space to one space
    stripped = re.sub('\s+', ' ', stripped)

    # Remove start and end white spaces
    stripped = stripped.strip()
    if stripped != '':
            return stripped.lower()

# Stopword removal 
stop_words = set(stopwords.words('english'))
your_list = ['skills', 'ability', 'job', 'description']
for i, line in enumerate(txt1):
    txt1[i] = ' '.join([x for 
        x in nltk.word_tokenize(line) if 
        ( x not in stop_words ) and ( x not in your_list )])

# Getting trigrams 
vectorizer = CountVectorizer(ngram_range = (3,3))
X1 = vectorizer.fit_transform(txt1) 
features = (vectorizer.get_feature_names())
print("\n\nFeatures : \n", features)
print("\n\nX1 : \n", X1.toarray())

# Applying TFIDF
vectorizer = TfidfVectorizer(ngram_range = (3,3))
X2 = vectorizer.fit_transform(txt1)
scores = (X2.toarray())
print("\n\nScores : \n", scores)

# Getting top ranking features
sums = X2.sum(axis = 0)
data1 = []
for col, term in enumerate(features):
    data1.append( (term, sums[0,col] ))
ranking = pd.DataFrame(data1, columns = ['term','rank'])
words = (ranking.sort_values('rank', ascending = False))
print ("\n\nWords head : \n", words.head(7))
```

**输出:**

```
Features : 
 ['10 experience working', '11 exposure implementing', 'able work minimal',
 'accounts commerce added', 'analysis recognition face', 'analytics contextual image',
 'analytics nlp ensemble', 'applying data science', 'bagging boosting text',
 'beyond existing learn', 'boosting text analytics', 'building using logistics',
 'building using supervised', 'classification facial expression', 
 'classifier deep learning', 'commerce added advantage',
 'complex engineering analysis', 'contextual image processing',
 'creative projects work', 'data science problem', 'data science solutions',
 'decisions report progress', 'deep learning analytics', 'deep learning framework',
 'deep learning neural', 'demonstrated development role', 'demonstrated leadership role',
 'description machine learning', 'detection tracking classification',
 'development role machine', 'direction project less', 'domains essential position',
 'domains like healthcare', 'ensemble classifier deep', 'existing learn quickly',
 'experience object detection', 'experience working multiple',
 'experienced technical personnel', 'expertise visualizing manipulating',
 'exposure implementing data', 'expression analysis recognition',
 'extensively worked python', 'face iris finger', 'facial expression analysis',
 'finance accounts commerce', 'forest bagging boosting', 'framework tensorflow keras',
 'good oral written', 'guidance direction project', 'guidance make decisions',
 'healthcare finance accounts', 'implementing data science', 'including provide guidance',
 'innovative creative projects', 'iris finger gesture', 'job description machine',
 'keras or pytorch', 'leadership role projects', 'learn quickly new',
 'learning analytics contextual', 'learning framework tensorflow',
 'learning neural networks', 'learning projects including', 'less experienced technical',
 'like healthcare finance', 'linear regression svm', 'logistics regression linear',
 'machine learning developer', 'machine learning projects', 'make decisions report',
 'manipulating big datasets', 'minimal guidance make', 'model building using',
 'motivated able work', 'multiple domains like', 'must self motivated',
 'new domains essential', 'nlp ensemble classifier', 'object detection tracking',
 'oral written communication', 'perform complex engineering', 'problem solving proven',
 'problem statements bring', 'proficiency deep learning', 'proficiency problem solving',
 'project less experienced', 'projects including provide', 'projects work spare',
 'proven perform complex', 'proven record working', 'provide guidance direction',
 'quickly new domains', 'random forest bagging', 'recognition face iris',
 'record working innovative', 'regression linear regression', 'regression svm random',
 'role machine learning', 'role projects including', 'science problem statements',
 'science solutions production', 'self motivated able', 'solutions production environments',
 'solving proven perform', 'spare time plus', 'statements bring insights',
 'supervised unsupervised algorithms', 'svm random forest', 'tensorflow keras or',
 'text analytics nlp', 'tracking classification facial', 'using logistics regression',
 'using supervised unsupervised', 'visualizing manipulating big', 'work minimal guidance',
 'work spare time', 'working innovative creative', 'working multiple domains']

X1 : 
 [[0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 ...
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]]

Scores : 
 [[0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 ...
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 0\. 0.]]

Words head : 
                             term      rank
41     extensively worked python  1.000000
79    oral written communication  0.707107
47             good oral written  0.707107
72          model building using  0.673502
27  description machine learning  0.577350
70     manipulating big datasets  0.577350
67    machine learning developer  0.577350
```

现在，如果我们为二元模型这样做，那么代码的初始部分将保持不变。只有二元模型形成部分会改变。 **代码:实现二元模型的 Python 代码**

```
# Getting bigrams 
vectorizer = CountVectorizer(ngram_range =(2, 2))
X1 = vectorizer.fit_transform(txt1) 
features = (vectorizer.get_feature_names())
print("\n\nX1 : \n", X1.toarray())

# Applying TFIDF
# You can still get n-grams here
vectorizer = TfidfVectorizer(ngram_range = (2, 2))
X2 = vectorizer.fit_transform(txt1)
scores = (X2.toarray())
print("\n\nScores : \n", scores)

# Getting top ranking features
sums = X2.sum(axis = 0)
data1 = []
for col, term in enumerate(features):
    data1.append( (term, sums[0, col] ))
ranking = pd.DataFrame(data1, columns = ['term', 'rank'])
words = (ranking.sort_values('rank', ascending = False))
print ("\n\nWords : \n", words.head(7))
```

**输出:**

```
X1 : 
 [[0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 ...
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]]

Scores : 
 [[0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 ...
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 0\. 0.]]

Words : 
                     term      rank
50   great interpersonal  1.000000
110     skills abilities  1.000000
23         deep learning  0.904954
72      machine learning  0.723725
21          data science  0.723724
128        worked python  0.707107
42    extensively worked  0.707107

```

同样，根据我们的使用，我们可以获得二元模型和三元模型的 TF IDF 分数。这些可以帮助我们获得更好的结果，而不必处理更多的数据。