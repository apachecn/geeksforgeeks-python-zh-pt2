# Python |将第 Kth 个字符与每个元素配对

> 原文:[https://www . geeksforgeeks . org/python-pair-kth-字符与每个元素/](https://www.geeksforgeeks.org/python-pair-kth-character-with-each-element/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要执行字符串中每个字符与其他字符的配对。这可以应用于许多领域，包括网络开发和日常工作。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这个任务可以使用循环来执行。这是一种可以执行这项任务的强力方式。在这种情况下，我们迭代每个字符，并将第 Kt 个字母附加到每个字符上，并构造一个列表。

```
# Python3 code to demonstrate working of 
# Pair Kth character with each element
# Using loop

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# initializing K 
K = 4

# Pair Kth character with each element
# Using loop
res = []
for ele in test_str:
        res.append(test_str[K] + ele)

# printing result 
print("List after pairing : " + str(res)) 
```

**Output :**

```
The original string is : geeksforgeeks
List after pairing : ['sg', 'se', 'se', 'sk', 'ss', 'sf', 'so', 'sr', 'sg', 'se', 'se', 'sk', 'ss']

```