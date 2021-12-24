# Python |替换字符串中的后字

> 原文:[https://www . geesforgeks . org/python-replace-后置字符串中的单词/](https://www.geeksforgeeks.org/python-replace-rear-word-in-string/)

有时，在处理字符串列表时，我们会遇到一个问题，需要替换字符串的最后一个单词。这个问题在 web 开发领域有很多应用。让我们讨论一下解决这个问题的不同方法。

**方法#1:使用`split() + join()`**
这是我们执行这个任务的一种方式。在本例中，我们将元素分成几部分，然后返回最后一个值，并使用 join()执行新元素的添加。

```py
# Python3 code to demonstrate working of
# Rear word replace in String
# using split() + join()

# initializing string 
test_str = "GFG is good"

# printing original string 
print("The original string is : " + test_str)

# initializing replace string 
rep_str = "best"

# Rear word replace in String
# using split() + join()
res =  " ".join(test_str.split(' ')[:-1] + [rep_str])

# printing result
print("The String after performing replace : " + res)
```

**Output :**

```py
The original string is : GFG is good
The String after performing replace : GFG is best

```