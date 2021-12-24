# 使用递归长短期记忆网络生成文本

> 原文:[https://www . geesforgeks . org/text-generation-use-recursive-long-short-memory-network/](https://www.geeksforgeeks.org/text-generation-using-recurrent-long-short-term-memory-network/)

本文将演示如何通过构建**递归长短期记忆网络**来构建**文本生成器**。训练网络的概念过程是首先向网络馈送网络正在训练的文本中存在的每个字符到唯一数字的映射。然后每个字符被热编码成一个矢量，这是网络所需的格式。
所述程序的数据从[卡格尔](https://www.kaggle.com/aashita/nyt-comments)下载。该数据集包含 2017 年 4 月至 2018 年 4 月发表在《纽约时报》上的文章。根据出版月份分开。数据集的形式为。csv 文件，包含已发布文章的 url 以及其他详细信息。任何一个随机的网址被选择用于训练过程，然后在访问这个网址时，文本被复制到一个文本文件中，这个文本文件被用于训练过程。
**第一步:导入需要的库**

## 蟒蛇 3

```
from __future__ import absolute_import, division,
                       print_function, unicode_literals

import numpy as np
import tensorflow as tf

from keras.models import Sequential
from keras.layers import Dense, Activation
from keras.layers import LSTM

from keras.optimizers import RMSprop

from keras.callbacks import LambdaCallback
from keras.callbacks import ModelCheckpoint
from keras.callbacks import ReduceLROnPlateau
import random
import sys
```

**第二步:将数据加载到字符串中**

## 蟒蛇 3

```
# Changing the working location to the location of the text file
cd C:\Users\Dev\Desktop\Kaggle\New York Times

# Reading the text file into a string
with open('article1.txt', 'r') as file:
    text = file.read()

# A preview of the text file   
print(text)
```

![](img/980b5b917f58d52bf060e2ff7df60b4e.png)

**第三步:创建从文本中每个唯一字符到唯一数字**
的映射

## 蟒蛇 3

```
# Storing all the unique characters present in the text
vocabulary = sorted(list(set(text)))

# Creating dictionaries to map each character to an index
char_to_indices = dict((c, i) for i, c in enumerate(vocabulary))
indices_to_char = dict((i, c) for i, c in enumerate(vocabulary))

print(vocabulary)
```

![](img/9b773b08e1d9e274bc7c2dc45990be98.png)

**第四步:数据预处理**

## 蟒蛇 3

```
# Dividing the text into subsequences of length max_length
# So that at each time step the next max_length characters
# are fed into the network
max_length = 100
steps = 5
sentences = []
next_chars = []
for i in range(0, len(text) - max_length, steps):
    sentences.append(text[i: i + max_length])
    next_chars.append(text[i + max_length])

# Hot encoding each character into a boolean vector
X = np.zeros((len(sentences), max_length, len(vocabulary)), dtype = np.bool)
y = np.zeros((len(sentences), len(vocabulary)), dtype = np.bool)
for i, sentence in enumerate(sentences):
    for t, char in enumerate(sentence):
        X[i, t, char_to_indices[char]] = 1
    y[i, char_to_indices[next_chars[i]]] = 1
```

**第五步:建设 LSTM 网络**

## 蟒蛇 3

```
# Building the LSTM network for the task
model = Sequential()
model.add(LSTM(128, input_shape =(max_length, len(vocabulary))))
model.add(Dense(len(vocabulary)))
model.add(Activation('softmax'))
optimizer = RMSprop(lr = 0.01)
model.compile(loss ='categorical_crossentropy', optimizer = optimizer)
```

**第 6 步:定义一些将在网络**
训练期间使用的辅助函数注意，下面给出的前两个函数是参考了来自 Keras 团队的[官方文本生成示例的文档。
a) **辅助函数采样下一个字符:**](https://github.com/keras-team/keras/blob/master/examples/lstm_text_generation.py) 

## 蟒蛇 3

```
# Helper function to sample an index from a probability array
def sample_index(preds, temperature = 1.0):
    preds = np.asarray(preds).astype('float64')
    preds = np.log(preds) / temperature
    exp_preds = np.exp(preds)
    preds = exp_preds / np.sum(exp_preds)
    probas = np.random.multinomial(1, preds, 1)
    return np.argmax(probas)
```

b) **帮助器功能生成每个纪元后的文本**

## 蟒蛇 3

```
# Helper function to generate text after the end of each epoch
def on_epoch_end(epoch, logs):
    print()
    print('----- Generating text after Epoch: % d' % epoch)

    start_index = random.randint(0, len(text) - max_length - 1)
    for diversity in [0.2, 0.5, 1.0, 1.2]:
        print('----- diversity:', diversity)

        generated = ''
        sentence = text[start_index: start_index + max_length]
        generated += sentence
        print('----- Generating with seed: "' + sentence + '"')
        sys.stdout.write(generated)

        for i in range(400):
            x_pred = np.zeros((1, max_length, len(vocabulary)))
            for t, char in enumerate(sentence):
                x_pred[0, t, char_to_indices[char]] = 1.

            preds = model.predict(x_pred, verbose = 0)[0]
            next_index = sample_index(preds, diversity)
            next_char = indices_to_char[next_index]

            generated += next_char
            sentence = sentence[1:] + next_char

            sys.stdout.write(next_char)
            sys.stdout.flush()
        print()
print_callback = LambdaCallback(on_epoch_end = on_epoch_end)
```

c) **帮助器功能，在损耗减少的每个时期后保存模型**

## 蟒蛇 3

```
# Defining a helper function to save the model after each epoch
# in which the loss decreases
filepath = "weights.hdf5"
checkpoint = ModelCheckpoint(filepath, monitor ='loss',
                             verbose = 1, save_best_only = True,
                             mode ='min')
```

d) **帮助器功能降低每次学习停滞时的学习率**

## 蟒蛇 3

```
# Defining a helper function to reduce the learning rate each time
# the learning plateaus
reduce_alpha = ReduceLROnPlateau(monitor ='loss', factor = 0.2,
                              patience = 1, min_lr = 0.001)
callbacks = [print_callback, checkpoint, reduce_alpha]
```

**第七步:训练 LSTM 模型**

## 蟒蛇 3

```
# Training the LSTM model
model.fit(X, y, batch_size = 128, epochs = 500, callbacks = callbacks)
```

![](img/b369ab532de87af3335c07ad3c937ad6.png)

**第八步:生成新的随机文本**

## 蟒蛇 3

```
# Defining a utility function to generate new and random text based on the
# network's learnings
def generate_text(length, diversity):
    # Get random starting text
    start_index = random.randint(0, len(text) - max_length - 1)
    generated = ''
    sentence = text[start_index: start_index + max_length]
    generated += sentence
    for i in range(length):
            x_pred = np.zeros((1, max_length, len(vocabulary)))
            for t, char in enumerate(sentence):
                x_pred[0, t, char_to_indices[char]] = 1.

            preds = model.predict(x_pred, verbose = 0)[0]
            next_index = sample_index(preds, diversity)
            next_char = indices_to_char[next_index]

            generated += next_char
            sentence = sentence[1:] + next_char
    return generated

print(generate_text(500, 0.2))
```

![](img/b53443252a4f141df3affa060330477a.png)