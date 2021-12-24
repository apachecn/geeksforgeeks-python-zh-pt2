# Python |根据大小提取前缀

> 原文:[https://www . geesforgeks . org/python-前缀-提取-取决于大小/](https://www.geeksforgeeks.org/python-prefix-extraction-depending-on-size/)

有时，在使用 Python 时，我们可能会遇到一个问题，需要从字符串中提取前缀。这有时可能是有条件的，如果字符串的大小大于某个 n，我们只需要提取特定长度的子字符串。让我们讨论执行此任务的某些方式。

**方法#1:使用循环**
这是执行这个任务的蛮力方式，其中我们使用循环根据大小提取字符串。

```
# Python3 code to demonstrate 
# Prefix extraction depending on size
# using loop

# Initializing list
test_list = ['geeksforgeeks', 'is', 'best', 'for', 'geeks']

# Initializing K 
K = 2

# Initializing N 
N = 4

# printing original list
print("The original list is : " + str(test_list))

# Prefix extraction depending on size
# using loop
res = []
for idx in test_list:
    if len(idx) >= N:
        res.append(idx[:K])

# printing result 
print ("List after prefix extraction : " + str(res))
```

**Output :**

```
The original list is : ['geeksforgeeks', 'is', 'best', 'for', 'geeks']
List after prefix extraction : ['ge', 'be', 'ge']

```