# Python–字符串中的短语提取

> 原文:[https://www . geesforgeks . org/python-短语-字符串提取/](https://www.geeksforgeeks.org/python-phrase-extraction-in-string/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们需要提取字符串中的某些单词，不包括开头和后面的 K 个单词。这可以应用于许多领域，包括所有包含数据的领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `enumerate()` +列表切片**
以上方法的结合可以解决这个问题。在这种情况下，我们提取空间的索引，并根据空间索引执行切片。

```py
# Python3 code to demonstrate working of 
# Phrase extraction in String
# Using list comprehension + enumerate() + list slicing

# initializing string
test_str = 'Geeksforgeeks is best for geeks and CS'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 2

# Phrase extraction in String
# Using list comprehension + enumerate() + list slicing
temp = [idx for idx, ele in enumerate(test_str) if ele == ' ']
res = test_str[temp[K - 1]: temp[-(K - 1)]].strip()

# printing result 
print("String after phrase removal : " + str(res)) 
```

**Output :**

```py
The original string is : Geeksforgeeks is best for geeks and CS
String after phrase removal : best for geeks and

```