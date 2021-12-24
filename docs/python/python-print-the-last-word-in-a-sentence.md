# Python–打印句子中的最后一个单词

> 原文:[https://www . geesforgeks . org/python-print-最后一句话/](https://www.geeksforgeeks.org/python-print-the-last-word-in-a-sentence/)

给定一个字符串，任务是编写一个 Python 程序来打印该字符串中的最后一个单词。

**示例:**

> **输入**:天空颜色为蓝色
> 
> **输出**:颜色
> 
> **解释:**颜色是句子中的最后一个词。
> 
> **输入**:在极客论坛学习算法
> 
> **输出**:极客 forgeek
> 
> **解释:**颜色是句子中的最后一个词。

**方法#1:** 使用[进行循环](https://www.geeksforgeeks.org/python-for-loops/) + [字符串连接](https://www.geeksforgeeks.org/python-string-concatenation/)

*   浏览句子
*   取一个空字符串， **newstring。**
*   以相反的顺序遍历字符串，并使用[字符串串联将字符添加到**新字符串**中。](https://www.geeksforgeeks.org/python-string-concatenation/)
*   打破循环，直到我们得到第一个空格字符。
*   反转**新字符串**并返回(是句子中的最后一个单词)。

下面是上述方法的实现:

## 蟒蛇 3

```
# Function which returns last word
def lastWord(string):

    # taking empty string
    newstring = ""

    # calculating length of string
    length = len(string)

    # traversing from last
    for i in range(length-1, 0, -1):

        # if space is occurred then return
        if(string[i] == " "):

            # return reverse of newstring
            return newstring[::-1]
        else:
            newstring = newstring + string[i]

# Driver code
string = "Learn algorithms at geeksforgeeks"
print(lastWord(string))
```

**输出:**

```
geeksforgeeks
```

**方法 2:** 使用[分裂()](https://www.geeksforgeeks.org/python-string-split/)方法

*   因为一个句子中的所有单词都用空格隔开。
*   我们要用 **split()** 把句子用空格分割。
*   我们将所有的单词用空格分开，并存储在一个列表中。
*   列表中的最后一个元素是答案

下面是上述方法的实现:

## 蟒蛇 3

```
# Function which returns last word
def lastWord(string):

    # split by space and converting
    # string to list and
    lis = list(string.split(" "))

    # length of list
    length = len(lis)

    # returning last element in list
    return lis[length-1]

# Driver code
string = "Learn algorithms at geeksforgeeks"
print(lastWord(string))
```

**输出:**

```
geeksforgeeks
```