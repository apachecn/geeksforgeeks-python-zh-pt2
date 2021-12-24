# Python |使用字典从字符集提取单词

> 原文:[https://www . geesforgeks . org/python-单词-从字符集中提取-使用字典/](https://www.geeksforgeeks.org/python-words-extraction-from-set-of-characters-using-dictionary/)

给定单词，任务是使用定义的字典从一组字符中提取不同的单词。
**方法:**
Python 在其语言中定义了一个处理与单词相关的某些操作的内置模块`enchant`。在上述方法中，使用了以下方法。

*   `**check() :**`检查字符串是否为单词，如果字符串为单词则返回 true，否则返回 false。
*   `**permutations(str_arr, str_len) :**` 按照所述字符串长度提供字符串的组合。

有可能`enchant()`模块不存在，所以可以使用 *pip3 安装附魔*来安装。

**下面是上述方法的 Python 代码实现。**

```py
# importing libraries
import keyword
import enchant
from itertools import permutations 

d = enchant.Dict("en_US")

words = []
perm_word = []

# character combination to 
# list down all the words
str_arr = "star"

# Getting the string length to use it in the loop. 
str_len = 4
print("Length of the string is : ", str_len )

while str_len > 1 :

    if str_len == len(str_arr):
        perm = list(permutations(str_arr))
        str_len = str_len -1

        for i in list(perm):
            words =''.join(i)

            if d.check(words):
                perm_word.append(words)
                print ( words + " is an English words")
        print ("perm_word", perm_word)

    elif str_len > 1:
        perm = list(permutations(str_arr, str_len))
        str_len = str_len -1

        for i in list(perm):
            words =''.join(i)

            if d.check(words):
                perm_word.append(words)
                print ( words + " is an English word")
        print ("perm_word", perm_word)

    else:
        str_len = 0
```

**输出:**

```py
star is an English words
tars is an English words
arts is an English words
rats is an English words
perm_word [‘star’, ‘tars’, ‘arts’, ‘rats’]
sat is an English word
tar is an English word
art is an English word
rat is an English word
perm_word [‘star’, ‘tars’, ‘arts’, ‘rats’, ‘sat’, ‘tar’, ‘art’, ‘rat’]
st is an English word
ts is an English word
tr is an English word
as is an English word
at is an English word
rs is an English word
rt is an English word
perm_word [‘star’, ‘tars’, ‘arts’, ‘rats’, ‘sat’, ‘tar’, ‘art’, ‘rat’, 
‘st’, ‘ts’, ‘tr’, ‘as’, ‘at’, ‘rs’, ‘rt’]
```