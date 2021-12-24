# Python |颠倒一个句子中的每个单词

> 原文:[https://www.geeksforgeeks.org/python-reverse-word-sentence/](https://www.geeksforgeeks.org/python-reverse-word-sentence/)

给定一个长句子，在句子本身中分别颠倒句子的每个单词。
示例:

```py
Input : Geeks For Geeks is good to learn
Output : skeeG roF skeeG si doog ot nrael

Input : Split Reverse Join
Output : tilpS esreveR nioJ

```

我们将使用 Python 的内置库函数来分别反转字符串本身中的每个单词。

**先决条件:**
1。[分裂()](https://www.geeksforgeeks.org/how-to-split-a-string-in-cc-python-and-java/)T5】2。[Python 中的反转技术](https://www.geeksforgeeks.org/reverse-string-python-5-different-ways/)
3。[python 中的列表理解法](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)
4。[连接()](https://www.geeksforgeeks.org/join-function-python/)

*   首先把句子分成单词列表。
*   分别反转列表中字符串的每个单词。
*   把列表中的单词连接起来组成一个新句子。

**下面是上面思路的实现。**

```py
# Python code to Reverse each word
# of a Sentence individually

# Function to Reverse words
def reverseWordSentence(Sentence):

    # Splitting the Sentence into list of words.
    words = Sentence.split(" ")

    # Reversing each word and creating
    # a new list of words
    # List Comprehension Technique
    newWords = [word[::-1] for word in words]

    # Joining the new list of words
    # to for a new Sentence
    newSentence = " ".join(newWords)

    return newSentence

# Driver's Code 
Sentence = "GeeksforGeeks is good to learn"
# Calling the reverseWordSentence 
# Function to get the newSentence
print(reverseWordSentence(Sentence))
```

输出:

```py
skeeGrofskeeG si doog ot nrael

```

Python 以其短代码而闻名。我们将做同样的任务，但代码较少。

```py
# Python code to Reverse each word
# of a Sentence individually

# Function to Reverse words
def reverseWordSentence(Sentence):

    # All in One line
    return ' '.join(word[::-1] for word in Sentence.split(" "))

# Driver's Code 
Sentence = "Geeks for Geeks"
print(reverseWordSentence(Sentence))    
```

输出:

```py
skeeG rof skeeG

```