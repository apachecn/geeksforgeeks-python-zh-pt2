# 文本中的情感–基于单词的编码

> 原文:[https://www . geesforgeks . org/基于文字的情感编码/](https://www.geeksforgeeks.org/sentiments-in-text-word-based-encodings/)

**情感分析**是描述某一特定感觉或观点是积极的、消极的还是中性的过程。例如“我讨厌我的午餐”、“我喜欢我的午餐”和“我对我的午餐很满意”。这些句子都有否定、肯定和中性的语气。在很大程度上，情感分析用于通过评论确定客户的反馈。这些评论有助于建立推荐系统以供将来参考。

## 如何在一个句子中得到一个单词的意思？

我们可以获取字符的 ASCII 值，但这有助于我们理解单词的语义吗？。让我们考虑一下“二进制”这个词，它也可以写成“聪明”。很明显，这两个词共享相同的 ASCII 值，但意义完全不同。用单词训练神经网络是一项艰巨的任务。所有这些的解决方案是，我们是否可以赋予单词价值，并在训练模型中使用它们

考虑这句话“我爱我的午餐”让我们给它一些随机数。假设值分别为 1、2、3 和 4。假设我们有另一句话是“我爱我的猫”，我们可以重用以前的价值观，给“猫”这个词一个新的象征。假设这只猫的价值是 5 英镑。这两个句子中有 4 个相似值。这是如何训练神经网络的开始。幸运的是，我们有像 **Tensorflow** 这样的 API。按照以下步骤训练您的模型

*   **步骤 1:** 导入所需的库
*   **步骤 2:** 创建一个句子列表
*   **步骤 3:** 创建标记器对象
*   **步骤 4:** 使用 fit_on_text 方法
*   **第五步:**打印出 word_index

下面是实现。

```py
import tensorflow as tf
from tensorflow import keras
from tensorflow.keras.preprocessing.text import Tokenizer

sentences = [
    "I love my lunch",
    "I love my cat !"
]

tokenizer = Tokenizer(num_words = 100)
tokenizer.fit_on_texts(sentences)
word_index = tokenizer.word_index

print(word_index)
```

**输出:**

```py
{'i': 1, 'love': 2, 'my': 3, 'lunch': 4, 'cat': 5}
```