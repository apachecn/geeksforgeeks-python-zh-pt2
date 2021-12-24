# Python 中的拼写检查器

> 原文:[https://www.geeksforgeeks.org/spelling-checker-in-python/](https://www.geeksforgeeks.org/spelling-checker-in-python/)

对于任何类型的文本处理或分析，检查单词的拼写是基本要求之一。本文讨论了各种检查单词拼写的方法，也可以纠正相应单词的拼写。

## 使用 textblob 库

首先需要在命令提示符下使用 pip 安装库 **textblob** 。

```
pip install textblob

```

您也可以在 Jupyter 笔记本中安装此库，如下所示:

## 蟒蛇 3

```
import sys
!{sys.executable} - m pip install textblob
```

**拼写检查程序–**

## 蟒蛇 3

```
from textblob import TextBlob

a = "cmputr"           # incorrect spelling
print("original text: "+str(a))

b = TextBlob(a)

# prints the corrected spelling
print("corrected text: "+str(b.correct()))
```

**输出:**

```
original text: cmputr
corrected text: computer

```

## 使用 pyspellchecker 库

您可以使用 pip: 如下所示安装此库:

```
pip install pyspellchecker 
```

****在 Jupyter 笔记本中:**T2】**

## **蟒蛇 3**

```
import sys
!{sys.executable} - m pip install pyspellchecker
```

 ****使用 pyspellchecker 的拼写检查程序–**** 

## **蟒蛇 3**

```
from spellchecker import SpellChecker

spell = SpellChecker()

# find those words that may be misspelled
misspelled = spell.unknown(["cmputr", "watr", "study", "wrte"])

for word in misspelled:
    # Get the one `most likely` answer
    print(spell.correction(word))

    # Get a list of `likely` options
    print(spell.candidates(word))
```

****输出:**** 

```
computer
{'caput', 'caputs', 'compute', 'computor', 'impute', 'computer'}
water
{'water', 'watt', 'warr', 'wart', 'war', 'wath', 'wat'}
write
{'wroe', 'arte', 'wre', 'rte', 'wrote', 'write'} 
```

## **使用 JamSplast**

**要在进行拼写纠正的同时达到最佳质量，基于字典的方法是不够的。你需要考虑周围这个词。jamsplash 是一个基于语言模型的 python 拼写检查库。它针对不同的上下文进行不同的更正。**

**1)安装开关 3**

```
apt-get install swig3.0   # for linux
brew install swig@3       # for mac 
```

**2)安装 jamspell**

```
pip install jamspell 
```

**3) [下载](https://github.com/bakwc/JamSpell#download-models)你的语言的语言模型**

## **蟒蛇 3**

```
# Create a corrector
corrector = jamspell.TSpellCorrector()

# Load Language model -
# argument is a downloaded model file path
corrector.LoadLangModel('Downloads/en_model.bin')

# To fix text automatically run FixFragment:
print(corrector.FixFragment('I am the begt spell cherken!'))

# To get a list of possible candidates
# pass a splitted sentence, and a word position
print(corrector.GetCandidates(['i', 'am', 'the', 'begt', 'spell', 'cherken'], 3))

print(corrector.GetCandidates(['i', 'am', 'the', 'begt', 'spell', 'cherken'], 5))
```

****输出:****

```
u'I am the best spell checker!'
(u'best', u'beat', u'belt', u'bet', u'bent')
(u'checker', u'chicken', u'checked', u'wherein', u'coherent', ...) 
```