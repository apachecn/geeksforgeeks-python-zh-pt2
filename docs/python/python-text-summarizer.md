# Python |文本摘要器

> 原文:[https://www.geeksforgeeks.org/python-text-summarizer/](https://www.geeksforgeeks.org/python-text-summarizer/)

如今，各种组织，无论是网上购物、政府和私营部门组织、餐饮和旅游业还是其他提供客户服务的机构，都关心他们的客户，并在我们每次使用他们的服务时要求反馈。考虑这样一个事实，这些公司可能每天都会收到大量的用户反馈。对于管理层来说，坐下来分析每一个问题将变得相当乏味。
但是，今天的技术已经达到了可以完成人类所有任务的程度。让这些事情发生的领域是机器学习。这些机器已经能够使用自然语言处理来理解人类语言。今天，文本分析领域的研究正在进行。
文本分析和自然语言处理的一个这样的应用是**反馈总结器**，它有助于总结和缩短用户反馈中的文本。这可以通过一种算法来减少正文，但保持其原始含义，或者对原始文本进行深入了解。

如果你对数据分析感兴趣，你会发现学习自然语言处理非常有用。Python 为自然语言处理提供了巨大的库支持。我们将使用自然语言工具包。这将服务于我们的目的。

使用:
`sudo pip install nltk`在您的系统上安装 NLTK 模块

让我们了解步骤–
**步骤 1:** 导入所需的库

有两个 NLTK 库对于构建一个高效的反馈总结器是必要的。

```
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize, sent_tokenize
```

**所用术语:**

***   corpus**

**语料库**
语料库是指文本的集合。它可以是包含文本的任何东西的数据集，无论是某个诗人的诗歌，某个作者的作品，等等。在这种情况下，我们将使用一组预先确定的停止词。*   **Tokenizers**
    it divides a text into a series of tokens. There are three main tokenizers – word, sentence, and regex tokenizer. We will only use the word and sentence tokenizer

    **步骤 2:** 删除停止词，并将其存储在单独的词数组中。

    **停止词**

    任何不增加句子意义的词，如(is，a，an，the，for)。例如，假设我们有一个句子

    ```
     GeeksForGeeks is one of the most useful websites for competitive programming.

    ```

    删除停止词后，我们可以缩小单词的数量并保留其含义，如下所示:

    ```
    ['GeeksForGeeks', 'one', 'useful', 'website', 'competitive', 'programming', '.']

    ```

    **第三步:**创建一个单词频率表
    一个 python 字典，它会记录每个单词在删除停止单词后在反馈中出现的次数。我们可以在每个句子上使用字典来知道哪些句子在整个文本中具有最相关的内容。

    ```
    stopWords = set(stopwords.words("english"))
    words = word_tokenize(text)
    freqTable = dict()
    ```

    **第四步:**根据句子包含的单词和频率表给每个句子打分

    我们可以使用**send _ token ize()**方法来创建句子数组。其次，我们需要一个字典来保存每个句子的分数，我们稍后会通过字典来生成摘要。

    ```
    sentences = sent_tokenize(text)
    sentenceValue = dict()
    ```

    **第五步:**给反馈内的句子分配一定的分值进行对比。
    比较分数的一个简单方法是找出一个句子的平均分数。平均值本身可以是一个很好的阈值。

    ```
    sumValues = 0
    for sentence in sentenceValue:
        sumValues += sentenceValue[sentence]
    average = int(sumValues / len(sentenceValue))
    ```

    应用阈值，将句子按顺序存储到摘要中。

    **代码:使用 Python 完成文本摘要器的实现**

    ```
    # importing libraries
    import nltk
    from nltk.corpus import stopwords
    from nltk.tokenize import word_tokenize, sent_tokenize

    # Input text - to summarize 
    text = """ """

    # Tokenizing the text
    stopWords = set(stopwords.words("english"))
    words = word_tokenize(text)

    # Creating a frequency table to keep the 
    # score of each word

    freqTable = dict()
    for word in words:
        word = word.lower()
        if word in stopWords:
            continue
        if word in freqTable:
            freqTable[word] += 1
        else:
            freqTable[word] = 1

    # Creating a dictionary to keep the score
    # of each sentence
    sentences = sent_tokenize(text)
    sentenceValue = dict()

    for sentence in sentences:
        for word, freq in freqTable.items():
            if word in sentence.lower():
                if sentence in sentenceValue:
                    sentenceValue[sentence] += freq
                else:
                    sentenceValue[sentence] = freq

    sumValues = 0
    for sentence in sentenceValue:
        sumValues += sentenceValue[sentence]

    # Average value of a sentence from the original text

    average = int(sumValues / len(sentenceValue))

    # Storing sentences into our summary.
    summary = ''
    for sentence in sentences:
        if (sentence in sentenceValue) and (sentenceValue[sentence] > (1.2 * average)):
            summary += " " + sentence
    print(summary)
    ```

    **输入:**

    > 有许多技术可以用来生成提取摘要，以保持其简单性，我将使用无监督学习方法来找到句子相似性并对它们进行排名。总结可以被定义为在保留关键信息和整体意义的同时产生简洁流畅的总结的任务。这样做的一个好处是，在开始将模型用于您的项目之前，您不需要培训和构建模型。理解余弦相似性有助于充分利用您将要看到的代码。余弦相似性是内积空间的两个非零向量之间的相似性度量，它度量它们之间角度的余弦。它测量向量之间角度的余弦。如果句子相似，角度将为 0。

    **输出**

    > 有许多技术可以生成摘要。总结可以被定义为在保留关键信息和整体意义的同时产生简洁流畅的总结的任务。这样做的一个好处是，在开始将模型用于您的项目之前，您不需要培训和构建模型。余弦相似性是内积空间的两个非零向量之间的相似性度量，它度量它们之间角度的余弦。