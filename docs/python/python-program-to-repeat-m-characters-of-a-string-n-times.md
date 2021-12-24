# Python 程序将一个字符串的 M 个字符重复 N 次

> 原文:[https://www . geesforgeks . org/python-program-to-repeat-m-characters-of-a-string-n-times/](https://www.geeksforgeeks.org/python-program-to-repeat-m-characters-of-a-string-n-times/)

在本文中，任务是编写一个 Python 程序，将字符串的 M 个字符重复 N 次。

**方法 1:**

1.  定义一个函数，将一个单词，m，n 个值作为参数。
2.  如果 M 大于单词的长度。将 m 值设置为等于单词的长度
3.  现在使用切片将需要重复的字符存储到名为 repeat_string 的字符串中。
4.  初始化名为的空字符串作为结果
5.  将 repeat_string 与结果连接 n 次。
6.  现在打印字符串。

**下面是实现:**

## 蟒蛇 3

```
def repeat(word, m, n):

    # if number of characters greater than length of word.
    # set number of characters = length of word
    if(m > len(word)):
        m = len(word)

    repeat_word = word[:m]
    result = ""

    for i in range(n):
        result = result+repeat_word
    print(result)

# driver code
repeat("geeks", 2, 3)
```

**输出:**

```
gegege
```

**方法二:**

1.  定义一个函数，该函数将一个单词，m，n 个值作为参数。
2.  如果 M 大于字长。将 m 值设置为等于单词长度
3.  现在使用切片将需要重复的字符存储到名为 repeat_string 的字符串中。
4.  将 repeat_string 乘以 n。
5.  现在打印字符串。

## 蟒蛇 3

```
def repeat(word, m, n):

    # if number of characters greater than length of word.
    # set number of characters = length of word
    if(m > len(word)):
        m = len(word)

    repeat_word = word[:m]
    print(repeat_word*n)

# driver code
repeat("geeks", 2, 3)
```

**输出:**

```
gegege
```