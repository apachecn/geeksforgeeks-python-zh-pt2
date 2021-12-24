# Python |使用 spaCy 的命名实体识别(NER)

> 原文:[https://www . geesforgeks . org/python-named-entity-recognition-ner-using-spacy/](https://www.geeksforgeeks.org/python-named-entity-recognition-ner-using-spacy/)

**命名实体识别(NER)** 是一个标准的 NLP 问题，涉及到识别命名实体(人、地点、组织等)。)并将其分类到一组预定义的类别中。NER 的一些实际应用包括:

*   为报道的人、组织和地点扫描新闻文章。
*   为搜索优化提供简洁的功能:人们可以简单地搜索相关的主要实体，而不是搜索整个内容。
*   快速检索推特帖子中谈论的地理位置。

**带 spaCy 的 NER**
spaCy 被认为是 Python 中速度最快的 NLP 框架，它实现的每个 NLP 任务都有单一的优化功能。由于易于学习和使用，人们可以使用几行代码轻松执行简单的任务。

**安装:**

```py
pip install spacy
python -m spacy download en_core_web_sm

```

**使用 spaCy 对 NER 进行编码。**

```py
import spacy

nlp = spacy.load('en_core_web_sm')

sentence = "Apple is looking at buying U.K. startup for $1 billion"

doc = nlp(sentence)

for ent in doc.ents:
    print(ent.text, ent.start_char, ent.end_char, ent.label_)
```

**输出**

```py
Apple 0 5 ORG
U.K. 27 31 GPE
$1 billion 44 54 MONEY

```

在输出中，第一列指定实体，接下来的两列指定句子/文档中的开始和结束字符，最后一列指定类别。

此外，有趣的是，spaCy 的 NER 模型使用大写字母作为识别命名实体的线索之一。同一个例子，当稍加修改测试时，会产生不同的结果。

```py
import spacy

nlp = spacy.load('en_core_web_sm')

sentence = "apple is looking at buying U.K. startup for $1 billion"

doc = nlp(sentence)

for ent in doc.ents:
    print(ent.text, ent.start_char, ent.end_char, ent.label_)
```

**输出**

```py
U.K. 27 31 GPE
$1 billion 44 54 MONEY

```

“苹果”这个词不再以命名实体的形式出现。因此，在通常的归一化或词干预处理步骤之前使用 NER 是很重要的。

人们也可以用自己的例子来训练和修改 spaCy 的内置 NER 模型。有几种方法可以做到这一点。下面的代码展示了一种简单的方法来引入新的实例并更新模型。

```py
import spacy
from spacy.gold import GoldParse
from spacy.language import EntityRecognizer

nlp = spacy.load('en', entity = False, parser = False)

doc_list = []
doc = nlp('Llamas make great pets.')
doc_list.append(doc)
gold_list = []
gold_list.append(GoldParse(doc, [u'ANIMAL', u'O', u'O', u'O']))

ner = EntityRecognizer(nlp.vocab, entity_types = ['ANIMAL'])
ner.update(doc_list, gold_list)
```

通过在 doc_list 中添加足够多的示例，可以使用 spaCy 生成定制的 NER。

spaCy 支持以下实体类型:
PERSON、NORP(民族、宗教和政治团体)、FAC(建筑、机场等)。)，ORG(组织)，GPE(国家，城市等。)，LOC(山脉、水体等)。)、产品(产品)、事件(事件名称)、艺术作品(书籍、歌曲标题)、法律(法律文件标题)、语言(命名语言)、日期、时间、百分比、金钱、数量、序数和基数。

**参考文献**

*   https://spacy.io/