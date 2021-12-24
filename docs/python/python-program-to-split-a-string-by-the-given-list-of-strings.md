# Python 程序根据给定的字符串列表分割字符串

> 原文:[https://www . geesforgeks . org/python-按给定字符串列表对字符串进行程序拆分/](https://www.geeksforgeeks.org/python-program-to-split-a-string-by-the-given-list-of-strings/)

给定一个字符串列表。任务是按照给定的字符串列表拆分字符串。

> **输入**:test _ str = ' geek forgeks stforgeks '，sub_list = ["best"]
> **输出**:[' geek forgeks '，' best '，' forgeek ']
> **解释** : "best "作为不同列表元素提取。
> 
> **输入**:test _ str = ' geekforgeksetforgeekscs '，sub_list = ["best "、" CS"]
> **输出** : ['geekforgeeks '，' best '，' forgeeks '，' CS"]
> **解释** : "best "和" CS "作为不同的列表元素提取。

**方法:使用 re.split() + |运算符**

在本例中，我们使用带有|运算符的 regex split()执行 split 任务，以检查需要单独放置的所有单词。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Separate specific Strings
# Using re.split() + | operator
import re

# initializing string
test_str = 'geekforgeeksisbestforgeeks'

# printing original String
print("The original string is : " + str(test_str))

# initializing list words 
sub_list = ["best"]

# regex to for splits()
# | operator to include all strings 
temp = re.split(rf"({'|'.join(sub_list)})", test_str)
res = [ele for ele in temp if ele] 

# printing result 
print("The segmented String : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeksisbestforgeeks
The segmented String : ['geekforgeeksis', 'best', 'forgeeks']

```