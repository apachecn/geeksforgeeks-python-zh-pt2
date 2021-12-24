# 使用名词短语和 CDF 概念的单词预测

> 原文:[https://www . geesforgeks . org/word-prediction-use-of-n-gram-and-CDF/](https://www.geeksforgeeks.org/word-prediction-using-concepts-of-n-grams-and-cdf/)

**对**–[CDF](https://en.wikipedia.org/wiki/Cumulative_distribution_function)和[N–克](https://blog.xrds.acm.org/2017/10/introduction-n-grams-need/)
**问题陈述**–给定任何输入单词和文本文件，预测文本文件中输入单词后可能出现的下 N 个单词。

**示例:**

```py
Input  :  is 
Output :  is it simply makes sure that there are never

Input  :  is
Output :  is split, all the maximum amount of objects, it

Input  :  the
Output : the exact same position. There will be some.
```

**注意**–为了举例说明，我给一些文本分配了可变语料库。如果你想在真实世界的文本数据上测试数据，你可以在这里找到数据[。](https://gagantalreja.github.io/wordPred/)

**解法**–我们可以用概率的概念来处理这个问题。首先，我们必须计算所有单词在文本文件中输入后出现的频率(n-gram，这里是 1-gram，因为我们总是在整个数据文件中找到下一个 1 单词)。然后使用这些频率，计算所有这些单词的 CDF，并从中选择一个随机单词。为了选择这个随机词，我们取一个随机数，找到大于或等于该随机数的最小 CDF。我们这样做是因为我们希望每个案例都有最可能的答案。这可以通过 cdf 来实现，因为它给出了列表中每个单词的累积概率。
找到 CDF 后，我们可以很容易地找到对应的单词，并将该单词追加到输出字符串中。现在，如果你愿意，你也可以把这个单词附加到输入字符串中，然后发送整个字符串来重复这个过程，找到下一个单词，或者你可以直接发送你用 cdf 找到的单词。我用前一种方法做到了这一点。

**注意**–多次输入同一个单词会得到不同的输出。这取决于数据文件的大小。文件越大，不同输出的概率越大。

**上述算法的代码**

## 蟒蛇 3

```py
import random
from collections import Counter

# This function calculates the freq of the (i+1)th
# word in the whole corpus, where i is the index of
# the sentence or the word.

def next_word_freq(array, sentence):

    sen_len, word_list = len(sentence.split()), []

    for i in range(len(array)):

        # If the sentence matches the sentence in the range (i, i+x)
        # and the length is less than the length of the corpus, append
        # the word to word_list.

        if ' '.join(array[i : i + sen_len]).lower() == sentence.lower():

            if i + sen_len < len(array) - 1:

                word_list.append(array[i + sen_len])

    # Return the count of each word in word_list

    return dict(Counter(word_list))

# Calculate the CDF of each word in the
# Counter dictionary.

def CDF(d):

    prob_sum, sum_vals = 0, sum(d.values())

    for k, v in d.items():

        # Calculate the PMF of each word by dividing
        # the freq. by total of all frequencies then add
        # all the PMFs till ith word which is the CDF of
        # the ith word.

        pmf = v / sum_vals
        prob_sum += pmf
        d[k] = prob_sum

    # Return cdf dictionary

    return d

# The main function reads the sentence/word as input
# from user and reads the corpus file. For faster processing,
# we have taken only the first 1000 words.

def main(sent, x, n):

    # I am using this sample text here to illustrate the output.
    # If anyone wants to use a text file, he can use the same. The code
    # to read corpus from file has been commented below.

    # corpus = open('a.txt','r').read()

    corpus = '''text The chance is unlikely if not done programmatically.
    However, imagine the game spawning multiple players at a spawn point,
    this would be the exact same location. I'm not quite sure what you
    mean with spin,     what does the integer reflect? Why is it a
    mismatch between data and structure? The structure does not
    assume a set amount of objects, it can be anything, that's why new
    nodes are created. It simply makes sure that there are not more than
    X leafs inside 1 node. The random is no option of course.
    My splitting algorithm always created the maximum amount of nodes
    already, split over the current node. But I guess I have to change
    this behaviour? Actually, all the books have different authors. And
    most have a different location too. There will be some with the same
    location, but different authors, though. I think my library should be
    able to store books with the same position. There are never
    equally-attractive leaf nodes. If a node is split, all childs will
    reflect a different part of the parent node.'''

    l = corpus.split()

    # "temp_out" will be used to store each partial sentence
    # which will later be stored into "sent". "out" is used to store
    # the final output.

    temp_out = ''
    out = sent + ' '

    for i in range(n - x):

        # calling the next_word_freq method that returns
        # the frequency of each word next to sent in the
        # whole word corpus.

        func_out = next_word_freq(l, sent)

        # cdf_dict stores the cdf of each word in the above map
        # that is calculated using method CDF.

        cdf_dict = CDF(func_out)

        # We use a random number to predict the next word.
        # The word having its CDF greater than or equal to rand
        # and less than or equal to 1.

        rand = random.uniform(0, 1)

        # If cdf_dict is empty, it means the word.sentence entered by you
        # does not exist in the corpus. Hence, break the loop and just print
        # the word entered by you. To implement this we use try-except block.
        # If an error occurs it implies there aren't enough values to unpack
        # and this can happen only when your input is absent from the corpus.

        try: key, val = zip(*cdf_dict.items())
        except: break

        # Iterate through the cdf values and find the smallest value
        # greater than or equal to the random number. That value is the
        # cdf of your predicted word. Add the key of the value to the output
        # string and update the "sent" variable as "temp_out".

        for j in range(len(val)):

            if rand <= val[j]:
                pos = j
                break

        temp_out = key[pos]
        out = out + temp_out + ' '
        sent = temp_out

    print(out, end = '\n\n')

if __name__ == '__main__':

    inp_sent = 'is'
    # The output will have 10 words, including the input sentence/word.
    main(inp_sent, len(inp_sent), 10)

# Code contributed by Gagan Talreja.
```

上面显示的概念用于自然语言处理等领域。这是一个幼稚的方法，只是为了说明这个概念。事实上，有更多的算法可以用来预测单词。你可以在这里找到其中一个