# 将字典保存到文件中

> 原文:[https://www.geeksforgeeks.org/save-a-dictionary-to-a-file/](https://www.geeksforgeeks.org/save-a-dictionary-to-a-file/)

Python 中的[字典](https://www.geeksforgeeks.org/python-dictionary/)是一个集合，其中每个值都映射到一个键。它们是无序的、可变的，并且对存储在字典中的值和键的数据类型没有约束。这使得字典作为文件存储变得很棘手。了解更多字典[点击这里](https://www.geeksforgeeks.org/python-dictionary/)。

**语法:**

```
dictionary = {'geek': 1, 'supergeek': True, 4: 'geeky'}

```

## 将词典保存到文件

使用 Python 将字典保存到文件中有两种主要方法。

**1。文本文件**

在 Python 中保存字典最基本的方法是将它们作为字符串存储在文本文件中。该方法包括以下步骤:

*   Open the file in write/append text mode
*   Convert a dictionary into a string
*   Use write function

```
filehandler = open(filename, 'wt')
data = str(dictionary)
filehander.write(data)

```

将转换后的字符串输入文件

从字典中读取存储的文本文件是很麻烦的，这种方法应该只用于较小和非关键的程序。

**2。泡菜模块(推荐)**

Python 中的 pickle 模块主要用于数据持久性至关重要的数据科学等领域。pickle 模块将给定的数据作为一个序列化的字节序列存储到文件中，以后可以很容易地检索到这些文件。Pickle 模块支持各种 Python 对象，字典就是其中之一。该方法包括以下步骤:

*   Import pickle module
*   Open a file in write/append binary mode
*   Dump method using pickle module

```
filehandler = open(filename, 'wb')
pickle.dump(dictionary, filehandler)

```

将数据输入文件

下面是上述方法的实现。

**示例 1:写入文本文件**

## python 3

```
dictionary = {'geek': 1, 'supergeek': True, 4: 'geeky'}

try:
    geeky_file = open('geekyfile.txt', 'wt')
    geeky_file.write(str(dictionary))
    geeky_file.close()

except:
    print("Unable to write to file")
```