# Python |使用 spaCy 进行词性标注和引理

> 原文:[https://www . geesforgeks . org/python-词性标注-和-词条化-使用-spacy/](https://www.geeksforgeeks.org/python-pos-tagging-and-lemmatization-using-spacy/)

**spaCy** 是最好的文本分析库之一。spaCy 擅长大规模信息提取任务，是世界上速度最快的公司之一。这也是为深度学习准备文本的最好方法。spaCy 比 NLTKTagger 和 TextBlob 更快更准确。

**如何安装？**

```
pip install spacy
python -m spacy download en_core_web_sm

```

**西班牙顶级特色:**
1。非破坏性标记化
2。命名实体识别
3。支持 49+语言
4。9 种语言的 16 种统计模型
5。预训练单词向量
6。词性标注
7。标注依赖解析
8。句法驱动的句子分割

**导入加载库:**

```
import spacy

# python -m spacy download en_core_web_sm
nlp = spacy.load("en_core_web_sm")
```

**评论的词性标注:**

这是一种将单词识别为名词、动词、形容词、副词等的方法。

```
import spacy

# Load English tokenizer, tagger, 
# parser, NER and word vectors
nlp = spacy.load("en_core_web_sm")

# Process whole documents
text = ("""My name is Shaurya Uppal. 
I enjoy writing articles on GeeksforGeeks checkout
my other article by going to my profile section.""")

doc = nlp(text)

# Token and Tag
for token in doc:
  print(token, token.pos_)

# You want list of Verb tokens
print("Verbs:", [token.text for token in doc if token.pos_ == "VERB"])
```

**输出:**

```
My DET
name NOUN
is VERB
Shaurya PROPN
Uppal PROPN
. PUNCT
I PRON
enjoy VERB
writing VERB
articles NOUN
on ADP
GeeksforGeeks PROPN
checkout VERB
my DET
other ADJ
article NOUN
by ADP
going VERB
to ADP
my DET
profile NOUN
section NOUN
. PUNCT

# Verb based Tagged Reviews:-
Verbs: ['is', 'enjoy', 'writing', 'checkout', 'going']

```

**引理化:**

这是一个将一个单词的屈折形式组合在一起的过程，这样它们就可以作为一个单独的项目来分析，由单词的引理或字典形式来识别。

```
import spacy

# Load English tokenizer, tagger,
# parser, NER and word vectors
nlp = spacy.load("en_core_web_sm")

# Process whole documents
text = ("""My name is Shaurya Uppal. I enjoy writing
          articles on GeeksforGeeks checkout my other
          article by going to my profile section.""")

doc = nlp(text)

for token in doc:
  print(token, token.lemma_)
```

输出:

```
My -PRON-
name name
is be
Shaurya Shaurya
Uppal Uppal
. .
I -PRON-
enjoy enjoy
writing write
articles article
on on
GeeksforGeeks GeeksforGeeks
checkout checkout
my -PRON-
other other
article article
by by
going go
to to
my -PRON-
profile profile
section section
. .

```