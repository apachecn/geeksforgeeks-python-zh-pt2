# Python 程序计算一句话的字数

> 原文:[https://www . geesforgeks . org/python-程序到句子字数/](https://www.geeksforgeeks.org/python-program-to-count-words-in-a-sentence/)

数据预处理是文本分类中的一项重要任务。随着 Python 在数据科学领域的出现，拥有某些人手不足的人在其中占据上风是至关重要的。本文讨论了如何计算一个句子中的单词，它从空格分隔的单词开始，但也包括在特殊字符存在的情况下如何计数。让我们讨论执行此操作的特定方法。

**方法#1:使用`split()`**
`split` 功能从列表中获取单词是相当有用且通常相当通用的方法，但是一旦我们在列表中引入特殊字符，这种方法就会失败。

```
# Python3 code to demonstrate 
# to count words in string 
# using split()

# initializing string  
test_string = "Geeksforgeeks is best Computer Science Portal"

# printing original string
print ("The original string is : " +  test_string)

# using split()
# to count words in string
res = len(test_string.split())

# printing result
print ("The number of words in string are : " +  str(res))
```

**Output:**

> 原来的字符串是:Geeksforgeeks 是最好的计算机科学门户
> 字符串的字数是:6