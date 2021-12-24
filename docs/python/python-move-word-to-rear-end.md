# Python–将单词移到后端

> 原文:[https://www.geeksforgeeks.org/python-move-word-to-rear-end/](https://www.geeksforgeeks.org/python-move-word-to-rear-end/)

有时候，在使用 Python 字符串时，我们可能会遇到一个问题，我们需要找到一个单词并将其移动到字符串的末尾。这可以应用于许多领域，包括日常编程和学校编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用`replace() + "+" operator`**
上述功能的组合可用于执行该任务。在这种情况下，我们用空字符串替换元素，并将工作附加到字符串的末尾来执行这个任务。

```
# Python3 code to demonstrate working of 
# Move Word to Rear end
# Using replace() + "+" operator

# initializing string
test_str = 'Geeksforgeeks is best for geeks '

# printing original string
print("The original string is : " + str(test_str))

# initializing Substring
sub_str = 'best'

# Move Word to Rear end
# Using replace() + "+" operator
res = test_str.replace(sub_str, "") + str(sub_str)

# printing result 
print("The string after word removal : " + str(res)) 
```

**Output :**

```
The original string is : Geeksforgeeks is best for geeks 
The string after word removal : Geeksforgeeks is  for geeks best

```