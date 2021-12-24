# 从列表中提取关键词的 Python 程序

> 原文:[https://www . geesforgeks . org/python-从列表中提取程序-关键词/](https://www.geeksforgeeks.org/python-program-to-extract-keywords-from-a-list/)

给定字符串列表，提取所有关键词。

> **输入**:test _ list =【“Gfg 为真”、“其为全局获胜”、“尝试 Gfg”】、
> **输出**:【‘是’、‘真’、‘全局’、‘尝试’】
> **解释**:结果列表中所有字符串均为有效 Python 关键字。
> 
> **输入**:test _ list =【“try Gfg”】、
> **输出**:【‘try’】
> **解释** : try 用在 try/except block 中，因此有一个关键字。

**方法#1:使用 iskeyword() + split() +循环**

这是执行这项任务的方法之一。在本文中，我们使用 iskeyword()检查关键字，并使用 split()将字符串转换为单词。扩展到所有字符串的逻辑是使用循环实现的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Keywords from String List

# Using iskeyword() + loop + split()
import keyword

# initializing list
test_list = ["Gfg is True", "Gfg will yield a return",
             "Its a global win", "try Gfg"]

# printing original list
print("The original list is : " + str(test_list))

# iterating using loop
res = []
for sub in test_list:
   for word in sub.split():

       # check for keyword using iskeyword()
       if keyword.iskeyword(word):
           res.append(word)

# printing result
print("Extracted Keywords : " + str(res))
```

**输出:**

> 原始列表为:['Gfg 为真'，' Gfg 将产生回报'，'这是一个全局的胜利'，'尝试 Gfg']
> 提取的关键词:['是'，'真'，'产生'，'回报'，'全局'，'尝试'

**方法 2:使用列表理解**

这是执行这项任务的另一种方式。与上述方法类似，但在纸面上更加紧凑，使用与上述方法类似的功能。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Keywords from String List

# Using list comprehension
import keyword

# initializing list
test_list = ["Gfg is True", "Gfg will yield a return",
             "Its a global win", "try Gfg"]

# printing original list
print("The original list is : " + str(test_list))

# One-liner using list comprehension
res = [ele for sub in test_list for ele in sub.split() if keyword.iskeyword(ele)]

# printing result
print("Extracted Keywords : " + str(res))
```

**输出:**

> 原始列表为:['Gfg 为真'，' Gfg 将产生回报'，'这是一个全局的胜利'，'尝试 Gfg']
> 提取的关键词:['是'，'真'，'产生'，'回报'，'全局'，'尝试'