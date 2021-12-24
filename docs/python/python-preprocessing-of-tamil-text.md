# Python–泰米尔文本的预处理

> 原文:[https://www . geesforgeks . org/python-预处理-of-tamil-text/](https://www.geeksforgeeks.org/python-preprocessing-of-tamil-text/)

预处理是自然语言处理的主要部分。为了对任何文本进行高精度分类，干净的数据起着重要作用。因此，在进行分析或分类之前，自然语言处理的第一步是数据的预处理。许多 python 库支持英语的预处理。但是对于泰米尔语来说，可用的预处理库非常少。下面是一些泰米尔文本预处理技术的例子。

本文涉及的预处理技术有

*   Punctuation symbolization
*   Stop word deletion

### **标点符号删除:**

## 蟒蛇 3

```
# Importing python string function
import string     
# Printing Inbuilt punctuation function
print(string.punctuation)   
```

**输出:**

> ！" #$% & '()*+，-。/:;< = >？@[\]^_`{|}~
> 
> t5】

如果文本中有任何上述标点符号，将在预处理后删除。这可以通过使用 python 字符串模块来移除。

## 蟒 3

```
# Function for removing punctuation
def punctuation_remove(text_data): 
    # Appending non punctuated words
    punctuation ="".join([t for t in text_data if t not in string.punctuation])  
    return punctuation

# Passing input to the function
punctuation_removed = punctuation_remove("வெற்றி *பெற வேண்டும், என்ற பதற்றம் ^இல்லாமல் _இருப்பது தான் 'வெற்றி பெறுவதற்கான சிறந்த வழி.") 
print(punctuation_removed)
```

**输出:**T2㎡T3㎡㎡㎡﹗﹗﹗

**解释:**给定文本中的所有标点符号都被删除。

### **标记化:**

标记化只不过是将句子中的每个单词拆分成一个标记，用于进一步分类。为了将文本转换成标记，使用了 python 中的正则表达式模块。

## 蟒蛇 3

```
# importing python regular expression module
import re    

# Function for tokenization
def tokenization(text_data):
   # Splitting the sentence into words where space is found.
   tokens_text = re.split(' ',text_data)      
   return tokens_text

# Passing the punctuation removed text as parameter for tokenization  
tokenized_text = tokenization(punctuation_removed)  
print(tokenized_text)
```

**输出:**

> 【ⅱ】
> 
> > > -。

**解释:**一个句子中的所有单词都被拆分成代币。

### **停止单词删除:**

停止词是一种语言中经常使用的词。这些词对句子的意思来说是不必要的。可以通过使用 python 中的 NLTK 包来删除停止词。NLTK 包支持英语、法语、德语、芬兰语、意大利语等多种语言，但不支持泰米尔语。因此，在给定的链接中下载泰米尔语的停止词–[Github Link](https://github.com/AshokR/TamilNLP/blob/master/tamilnlp/Resources/TamilStopWords.txt)并将文件命名为 ***泰米尔语*** ，并将其放置在系统中的以下位置–“…。\ AppData \漫游\nltk_data\corpora\stopwords "

经过这个过程，NLTK 包支持的泰米尔语停话也

## python 3

```
# Importing Natural Language Toolkit python library
import nltk

# Storing all the Tamil stop words in the variable retrieved from the file ‘tamil’ 
stopwords = nltk.corpus.stopwords.words('tamil')  

# Function for removing stop words
def stopwords_remove(text_data):
    # Appending words which are not stop words  
    removed= [s for s in text_data if s not in stopwords]  
    return removed

# Passing tokenized text as parameter for removing stop words
stopwords_removed = stopwords_remove(tokenized_text) 
print(stopwords_removed)
```

**输出:**

> 【ⅱ】
> 
> > > -。

**说明:**去掉了停止词'வேண்டும்'、'என்ற'、'தான்'。