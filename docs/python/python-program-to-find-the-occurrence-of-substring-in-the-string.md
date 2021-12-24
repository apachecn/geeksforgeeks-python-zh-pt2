# Python 程序查找字符串中出现的子串

> 原文:[https://www . geesforgeks . org/python-program-to-find-in-string-substring 的出现次数/](https://www.geeksforgeeks.org/python-program-to-find-the-occurrence-of-substring-in-the-string/)

给定一个单词列表，提取字符串中出现这些单词的所有索引。

> **输入** : test_str = 'geeksforgeeks 最适合极客和 cs '，test _ list =[“best”，“geeks”]
> **输出** : [2，4]
> **解释** : best 和 geeks 分别出现在第 2 和第 4 个索引处。
> 
> **输入** : test_str = 'geeksforgeeks 最适合极客和 cs '，test _ list =[“best”、“geeks”、“is”]
> **输出**:【1、2、4】
> **解释** : is、best 和 geeks 分别出现在第 1、2、4 个索引处。

**方法一:使用列表理解+拆分()+索引()**

在本文中，我们使用 split()执行从句子中获取单词的任务，然后使用 index()将字符串列表中的单词与提取的字符串进行匹配。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Word occurrence positions in String
# Using list comprehension + split() + index()

# initializing string
test_str = 'geeksforgeeks is best for geeks and cs'

# printing original string
print("The original string is : " + str(test_str))

# initializing list 
test_list = ["best", "geeks", "cs"]

# using index() to get indices,
# list comprehension used to offer one liner
res = [test_str.split().index(ele) 
       for ele in test_str.split() if ele in test_list]

# printing result 
print("The indices list : " + str(res))
```

**Output**

```py
The original string is : geeksforgeeks is best for geeks and cs
The indices list : [2, 4, 6]

```

**方法 2:使用列表理解+枚举()+拆分()**

这是执行这项任务的另一种方式。在这个任务中，获取索引是使用 enumerate()完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Word occurrence positions in String
# Using list comprehension + enumerate() + split()

# initializing string
test_str = 'geeksforgeeks is best for geeks and cs'

# printing original string
print("The original string is : " + str(test_str))

# initializing list 
test_list = ["best", "geeks", "cs"]

# using enumerate() to get indices,
# list comprehension used to offer one liner
res = [idx for idx, ele in enumerate(test_str.split()) if ele in test_list]

# printing result 
print("The indices list : " + str(res))
```

**Output**

```py
The original string is : geeksforgeeks is best for geeks and cs
The indices list : [2, 4, 6]

```