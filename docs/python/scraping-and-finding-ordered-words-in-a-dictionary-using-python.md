# 使用 Python 在字典中抓取和查找有序单词

> 原文:[https://www . geesforgeks . org/scratch-and-find-ordered-in-dictionary-use-python/](https://www.geeksforgeeks.org/scraping-and-finding-ordered-words-in-a-dictionary-using-python/)

**什么是有序词？**

有序单词是字母按字母顺序出现的单词。例如**修道院** & **泥土**。其余的单词是无序的，例如**极客**

**手头的任务**

这个任务取自 Rosetta Code，并不像上面描述中听起来那么平凡。为了获得大量的单词，我们将使用在**http://www.puzzlers.org/pub/wordlists/unixdict.txt**上可用的在线词典，它有大约 2500 个单词的集合，由于我们将使用 python，我们可以通过抓取词典而不是将其作为文本文件下载，然后对其进行一些文件处理操作来实现。

**要求:**

```py
pip install requests
```

**代码**

方法是遍历整个单词，成对比较元素的 ascii 值，直到我们发现一个错误的结果，否则这个单词将被排序。
所以这个任务会分为 2 部分:
**刮**

1.  使用 python 库**请求**我们将从给定的网址获取数据
2.  将从网址获取的内容存储为字符串
3.  使用 UTF-8 解码通常在网络上编码的内容
4.  将长串内容转换成单词列表

**查找有序单词**

1.  遍历单词列表
2.  每个单词中每个相邻字符的 ASCII 值的成对比较
3.  如果一对是无序的，则存储错误的结果
4.  否则打印有序的单词

```py
# Python program to find ordered words
import requests

# Scrapes the words from the URL below and stores 
# them in a list
def getWords():

    # contains about 2500 words
    url = "http://www.puzzlers.org/pub/wordlists/unixdict.txt"
    fetchData = requests.get(url)

    # extracts the content of the webpage
    wordList = fetchData.content

    # decodes the UTF-8 encoded text and splits the 
    # string to turn it into a list of words
    wordList = wordList.decode("utf-8").split()

    return wordList

# function to determine whether a word is ordered or not
def isOrdered():

    # fetching the wordList
    collection = getWords()

    # since the first few of the elements of the 
    # dictionary are numbers, getting rid of those
    # numbers by slicing off the first 17 elements
    collection = collection[16:]
    word = ''

    for word in collection:
        result = 'Word is ordered'
        i = 0
        l = len(word) - 1

        if (len(word) < 3): # skips the 1 and 2 lettered strings
            continue

        # traverses through all characters of the word in pairs
        while i < l:         
            if (ord(word[i]) > ord(word[i+1])):
                result = 'Word is not ordered'
                break
            else:
                i += 1

        # only printing the ordered words
        if (result == 'Word is ordered'):
            print(word,': ',result)

# execute isOrdered() function
if __name__ == '__main__':
    isOrdered()
```

```py
Output:
aau: Word is ordered
abbe: Word is ordered
abbey: Word is ordered
abbot: Word is ordered
abbott: Word is ordered
abc: Word is ordered
abe: Word is ordered
abel: Word is ordered
abet: Word is ordered
abo: Word is ordered
abort: Word is ordered
accent: Word is ordered
accept: Word is ordered
...........................
...........................
...........................

```

**参考文献:**T2【罗塞塔代码】T3】

本文由 [Palash Nigam](https://www.linkedin.com/in/palash25) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。