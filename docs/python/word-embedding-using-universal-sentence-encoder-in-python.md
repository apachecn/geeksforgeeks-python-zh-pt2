# Python 中使用通用句子编码器的单词嵌入

> 原文:[https://www . geesforgeks . org/word-embedding-use-universal-句子-python 中的编码器/](https://www.geeksforgeeks.org/word-embedding-using-universal-sentence-encoder-in-python/)

与将单词表示成向量的单词嵌入技术不同，在句子嵌入中，整个句子或文本及其语义信息被映射成实数向量。这种技术使得理解和处理整个文本的有用信息成为可能，然后可以用它来更好地理解句子的上下文或意思。

在本文中，您将学习如何使用**通用句子编码器**为完整的句子创建向量。

**例如:**

让我们考虑两个句子:-

1.  你几岁了？
2.  你多大了？

以上两个句子意思相似，即我们试图询问这个人的年龄。在上面两个句子中，单个单词及其向量不会很好地洞察一个完整的句子试图传达什么，也无法区分这两个句子是否相似。所以在这种情况下，句子嵌入比单词嵌入表现更好。

有各种各样的句子嵌入技术，如 Doc2Vec、SentenceBERT、通用句子编码器等。

## 通用句子编码器

通用句子编码器将整个句子或文本编码成实数向量，可用于聚类、句子相似性、文本分类和其他自然语言处理任务。在 Apache-2.0 许可下，预训练模型在这里可用。使用深度平均网络( **DAN** )编码器，在大于单词长度的文本、句子、短语、段落等上训练预训练模型。

使用通用句子编码器实现句子嵌入:

在终端中运行代码以安装必要的库之前，运行这些命令。

> pip install "tensorflow>=2.0.0"
> 
> pip install –upgrade tensorflow-hub

**程序:**

## 蟒蛇 3

```py
# import necessary libraries
import tensorflow_hub as hub

# Load pre-trained universal sentence encoder model
embed = hub.load("https://tfhub.dev/google/universal-sentence-encoder/4")

# Sentences for which you want to create embeddings,
# passed as an array in embed()
Sentences = [
    "How old are you",
    "What is your age",
    "I love to watch Television",
    "I am wearing a wrist watch"
]
embeddings = embed(Sentences)

# Printing embeddings of each sentence
print(embeddings)

# To print each embeddings along with its corresponding 
# sentence below code can be used.
for i in range(len(Sentences)):
    print(Sentences[i])
    print(embeddings[i])
```

**输出:**

> tf。张量(
> 
> [[-0.06045125 -0.00204541  0.02656925 …  0.00764413 -0.02669661
> 
>    0.05110302]
> 
>  [-0.08415682 -0.08687923  0.03446117 … -0.01439389 -0.04546221
> 
>    0.03639965]
> 
>  [ 0.0816019  -0.01570276 -0.05659245 … -0.07133699  0.11040762
> 
>   -0.0071095 ]
> 
>  [-0.00369539  0.03064634 -0.05556112 …  0.01751423  0.0316496
> 
> -0.05139377]]，shape=(4，512)，dtype = float32)

**说明:**

上面的输出使用通用句子编码器将输入句子表示成它们相应的向量。