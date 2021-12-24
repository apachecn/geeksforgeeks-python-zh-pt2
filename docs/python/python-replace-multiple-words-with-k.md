# Python–用 K 替换多个单词

> 原文:[https://www . geesforgeks . org/python-replace-multi-word-with-k/](https://www.geeksforgeeks.org/python-replace-multiple-words-with-k/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，需要用一个单词替换多个单词。这可以应用于许多领域，包括日常编程和学校编程。让我们讨论执行这项任务的某些方法。

**方法一:使用`join() + split()` +列表理解**
以上功能的组合可以用来执行此任务。在这种情况下，我们将字符串拆分成单词，使用连接和列表理解来检查和替换列表单词。

```py
# Python3 code to demonstrate working of 
# Replace multiple words with K
# Using join() + split() + list comprehension

# initializing string
test_str = 'Geeksforgeeks is best for geeks and CS'

# printing original string
print("The original string is : " + str(test_str))

# initializing word list 
word_list = ["best", 'CS', 'for']

# initializing replace word 
repl_wrd = 'gfg'

# Replace multiple words with K
# Using join() + split() + list comprehension
res = ' '.join([repl_wrd if idx in word_list else idx for idx in test_str.split()])

# printing result 
print("String after multiple replace : " + str(res)) 
```

**Output :**

```py
The original string is : Geeksforgeeks is best for geeks and CS
String after multiple replace : Geeksforgeeks is gfg gfg geeks and gfg

```