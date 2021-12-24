# Python–使用 Affin 的情感分析

> 原文:[https://www . geesforgeks . org/python-情绪-分析-使用-affin/](https://www.geeksforgeeks.org/python-sentiment-analysis-using-affin/)

**Affinn**是由*芬·鲁普·尼尔森*开发的用于情感分析的最简单但流行的词汇。它包含 3300 多个单词，每个单词都有一个极性分数。在 python 中，这个词典有一个内置函数。

让我们看看它的语法-

**安装库:**

```
# code
print("GFG")
pip install afinn / 
#instaalling in windows
pip3 install afinn /
#installing in linux
!pip install afinn
#installing in jupyter
```

**代码:使用 Affin**

```
#importing necessary libraries
from afinn import Afinn
import pandas as pd

#instantiate afinn
afn = Afinn()

#creating list sentences
news_df = ['les gens pensent aux chiens','i hate flowers',
         'hes kind and smart','we are kind to good people']

# compute scores (polarity) and labels
scores = [afn.score(article) for article in news_df]
sentiment = ['positive' if score > 0 
                          else 'negative' if score < 0 
                              else 'neutral' 
                                  for score in scores]

# dataframe creation
df = pd.DataFrame()
df['topic'] =  news_df
df['scores'] = scores
df['sentiments'] = sentiment
print(df)
```

进行情感分析的 Python 代码

**输出:**

```
topic  scores sentiments
0  les gens pensent aux chiens     0.0    neutral
1               i hate flowers    -3.0   negative
2           hes kind and smart     3.0   positive
3   we are kind to good people     5.0   positive
```

这个库包最大的好处是可以找到不同语言的乐谱。

```
afn = Afinn(language = 'da')

#assigning 'da' danish to the object variable.
afn.score('du er den mest modbydelige tæve')
```

**输出:**

```
-5.0

```

因此，我们可以很容易地立即获得分数。