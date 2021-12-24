# Python |前后字符相似的字符串

> 原文:[https://www . geesforgeks . org/python-前后字符相似的字符串/](https://www.geeksforgeeks.org/python-strings-with-similar-front-and-rear-character/)

有时，在编程时，我们会遇到一个问题，需要检查每个字符串的前后字符。我们可能需要提取前后字符相似的所有字符串的计数。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，迭代列表的每个元素，检查每个字符串的前后字符，并增加计数器，以防我们找到匹配的。

```
# Python3 code to demonstrate working of
# Similar front and rear elements
# Using loop

# initialize list 
test_list = ['gfg', 'is', 'best', 'treat']

# printing original list 
print("The original list : " + str(test_list))

# Similar front and rear elements
# Using loop
count = 0
for ele in test_list:
    if ele[0] == ele[-1]:
        count = count + 1 

# printing result
print("Total Strings with similar front and rear elements : " + str(count))
```

**Output :**

```
The original list : ['gfg', 'is', 'best', 'treat']
Total Strings with similar front and rear elements : 2

```