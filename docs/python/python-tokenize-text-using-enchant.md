# Python–使用附魔

标记文本

> 原文:[https://www . geesforgeks . org/python-token ize-text-using-附魔/](https://www.geeksforgeeks.org/python-tokenize-text-using-enchant/)

`Enchant`是 Python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

`Enchant`还提供了 **`enchant.tokenize`** 模块对文本进行标记化。标记化包括从正文中拆分单词。

一些经常使用的术语是:

*   **语料库**–正文，单数。语料库是这个的复数。
*   **词汇**–单词及其含义。
*   **标记**–每一个“实体”都是基于规则分割的一部分。例如，当一个句子被“标记化”成单词时，每个单词都是一个标记。

我们将使用`get_tokenizer()`来标记文本。它将语言代码作为输入，并返回适当的标记化类。然后我们用一些文本实例化这个类，它将返回一个迭代器，该迭代器将产生包含在该文本中的单词。
标记器产生的项是形式(WORD，POS)的元组，其中 WORD 是标记化的单词，POS 是该单词所在的字符串位置。

```
# import the module
from enchant.tokenize import get_tokenizer

# the text to be tokenized 
text = ("Natural language processing (NLP) is a field " + 
       "of computer science, artificial intelligence " + 
       "and computational linguistics concerned with " +  
       "the interactions between computers and human " +  
       "(natural) languages, and, in particular, " +  
       "concerned with programming computers to " + 
       "fruitfully process large natural language " +  
       "corpora. Challenges in natural language " +  
       "processing frequently involve natural " + 
       "language understanding, natural language" +  
       "generation frequently from formal, machine" +  
       "-readable logical forms), connecting language " +  
       "and machine perception, managing human-" + 
       "computer dialog systems, or some combination " +  
       "thereof.")

# getting tokenizer class
tokenizer = get_tokenizer("en_US")

token_list =[]
for words in tokenizer(text):
    token_list.append(words)

# print the words with POS
print(token_list)
```

**输出:**

> [(“自然”，0)、(“语言”，8)、(“处理”，17)、(“NLP”，29)、(“是”，34)、(“一”，37)、(“场”，39)、(“的”，45)、(“计算机”，48)、(“科学”，57)、(“人工”，66)、(“智能”，77)、(“和”，90)、(“计算”，94)、(“语言学”，108)、(“关注”，120)、(“与”，130)、(“the” 323)、(“自然”，326)、(“语言”，334)、(“处理”，343)、(“频繁”，354)、(“涉及”，365)、(“自然”，373)、(“语言”，381)、(“理解”，390)、(“自然”，405)、(“语言生成”，413)、(“频繁”，432)、(“从”，443)、(“形式”，448)、(“机器”，456)、(“可读”，464)、()

只打印文字，不打印位置:

```
# print only the words
word_list =[]

for tokens in token_list:
    word_list.append(tokens[0])
print(word_list)
```

**输出:**

> [“自然”，“语言”，“处理”，“NLP”，“is”，“a”，“field”，“of”，“计算机”，“科学”，“人工”，“智能”，“and”，“计算”，“语言学”，“关注”，“与”，“the”，“交互”，“在”，“计算机”，“与”，“人类”，“自然”，“语言”，“与”，“在”，“特定”，“关注”，“与”，“编程”，“计算机”，“到”，“结果”，“过程”，“大”，“自然”，“语言”，“语料库”，“挑战”，“在”，“自然”，“语言”，“处理”，“频繁”，“涉及”，“自然”，“语言”，“理解”，“自然”，“语言生成”，“频繁”，“从”，“形式”，“机器可读”，“逻辑”，“形式”，“连接”，“语言”，“语言”