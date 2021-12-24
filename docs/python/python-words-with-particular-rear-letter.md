# Python–带特殊尾字母的单词

> 原文:[https://www . geesforgeks . org/python-word-with-special-后置字母/](https://www.geeksforgeeks.org/python-words-with-particular-rear-letter/)

有时，我们要求得到以特定字母结尾的单词。这种用例在普通编程项目或竞争性编程中非常常见。让我们讨论一下 Python 中处理这个问题的一些技巧。

**方法#1:使用列表理解+ `lower()`**
这个问题可以通过使用上述两个函数的组合来解决，列表理解执行将逻辑扩展到整个列表的任务，并且较低的函数检查与参数字母的目标单词的大小写不敏感性。

```
# Python3 code to demonstrate
# Words with Particular Rear letter
# using list comprehension + lower()

# initializing list
test_list = ['Akash', 'Nikhil', 'Manjeet', 'akshat']

# initializing check letter
check = 'T'

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + lower()
# Words with Particular Rear letter
res = [idx for idx in test_list if idx[len(idx) - 1].lower() == check.lower()]

# print result
print("The list of matching last letter : " + str(res))
```

**Output :**

```
The original list : ['Akash', 'Nikhil', 'Manjeet', 'akshat']
The list of matching last letter : ['Manjeet', 'akshat']

```