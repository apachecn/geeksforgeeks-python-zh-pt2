# Python 程序打印字符串中的偶数长度单词

> 原文:[https://www . geesforgeks . org/python-程序到打印-偶数长度字符串中的单词/](https://www.geeksforgeeks.org/python-program-to-print-even-length-words-in-a-string/)

给定一个字符串。任务是打印给定字符串中所有长度均匀的单词。

**示例:**

```py
Input: s = "This is a python language"
Output: This
        is
        python
        language 

Input: s = "i am muskan"
Output: am
        muskan

```

**方法:**使用[分裂()](https://www.geeksforgeeks.org/python-string-split/)功能分裂琴弦。使用[循环遍历字符串中的单词。使用](https://www.geeksforgeeks.org/loops-in-python/) [len()](https://www.geeksforgeeks.org/python-string-length-len/) 函数计算单词的长度。如果长度是偶数，则打印该单词。

下面是 Python 实现上述方法:

```py
# Python3 program to print 
#  even length words in a string 

def printWords(s):

    # split the string 
    s = s.split(' ') 

    # iterate in words of string 
    for word in s: 

        # if length is even 
        if len(word)%2==0:
            print(word) 

# Driver Code 
s = "i am muskan" 
printWords(s) 
```

**输出:**

```py
am
muskan

```