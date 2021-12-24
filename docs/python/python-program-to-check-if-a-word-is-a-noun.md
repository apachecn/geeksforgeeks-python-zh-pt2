# Python 程序检查一个单词是否是名词

> 原文:[https://www . geesforgeks . org/python-program-to-check-如果一个单词是名词/](https://www.geeksforgeeks.org/python-program-to-check-if-a-word-is-a-noun/)

给定一个单词，任务是编写一个 Python 程序来查找这个单词是否是名词或者是否使用 Python。

**示例:**

```py
Input: India
Output: India is noun.

Input: Writing
Output: Writing is not a noun.
```

有各种各样的库可以用来解决这个问题。

**方法 1** : [使用 NLTK](https://www.geeksforgeeks.org/part-speech-tagging-stop-words-using-nltk-python/) 进行词性标注

## 蟒蛇 3

```py
# import required modules
import nltk
nltk.download('averaged_perceptron_tagger')

# taking input text as India
text = "India"
ans = nltk.pos_tag()

# ans returns a list of tuple
val = ans[0][1]

# checking if it is a noun or not
if(val == 'NN' or val == 'NNS' or val == 'NNPS' or val == 'NNP'):
    print(text, " is a noun.")
else:
    print(text, " is not a noun.")
```

**输出:**

```py
India is a noun.
```

**方法 2:** [使用 Spacy](https://www.geeksforgeeks.org/python-pos-tagging-and-lemmatization-using-spacy/) 进行词性标注

## 蟒蛇 3

```py
# import required modules
import spacy
nlp = spacy.load("en_core_web_sm")

# taking input
text = "Writing"

# returns a document of object
doc = nlp(text)

# checking if it is a noun or not
if(doc[0].tag_ == 'NNP'):
    print(text, " is a noun.")
else:
    print(text, " is not a noun.")
```

**输出:**

```py
Writing is not a noun.
```