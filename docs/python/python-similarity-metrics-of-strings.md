# Python |字符串的相似性度量

> 原文:[https://www . geesforgeks . org/python-相似性-字符串度量/](https://www.geeksforgeeks.org/python-similarity-metrics-of-strings/)

由于计算机科学的许多领域，如机器学习、人工智能和网络开发领域对相似性计算的要求，这种特殊的实用程序现在非常受欢迎，因此计算任何给定容器之间相似性的技术可能非常有用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用朴素方法(`sum() + zip()` )**
我们可以使用朴素方法执行这个特定的任务，使用 sum 和 zip 函数，我们可以制定一个实用函数来计算两个字符串的相似度。

```py
# Python3 code to demonstrate 
# similarity between strings
# using naive method (sum() + zip())

# Utility function to compute similarity
def similar(str1, str2):
    str1 = str1 + ' ' * (len(str2) - len(str1))
    str2 = str2 + ' ' * (len(str1) - len(str2))
    return sum(1 if i == j else 0 
               for i, j in zip(str1, str2)) / float(len(str1))

# Initializing strings
test_string1 = 'Geeksforgeeks'
test_string2 = 'Geeks4geeks'

# using naive method (sum() + zip())
# similarity between strings
res = similar(test_string1, test_string2)

# printing the result
print ("The similarity between 2 strings is : " + str(res))
```

**Output :**

```py
The similarity between 2 strings is : 0.38461538461538464

```