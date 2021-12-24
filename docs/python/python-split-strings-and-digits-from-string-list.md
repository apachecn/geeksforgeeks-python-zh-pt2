# Python |从字符串列表中拆分字符串和数字

> 原文:[https://www . geesforgeks . org/python-从字符串列表中拆分字符串和数字/](https://www.geeksforgeeks.org/python-split-strings-and-digits-from-string-list/)

有时，在处理字符串列表时，我们可能会遇到一个问题，即需要从数字列表中移除周围的杂散字符或噪音。这可以是货币前缀、数字符号等形式。让我们讨论一下执行这项任务的方法。

**方法:使用列表理解+ `strip() + isdigit() + join()`**
以上功能的组合可以用来执行这个任务。在这种情况下，我们从字符串中识别出的数字中去除杂散字符并返回结果。

```
# Python3 code to demonstrate working of
# Extract digit from string list 
# using list comprehension + strip() + isdigit() + join()
from itertools import groupby

# initialize list 
test_list = ["-4", "Rs 25", "5 kg", "+15"]

# printing original list 
print("The original list : " + str(test_list))

# Extract digit from string list 
# using list comprehension + strip() + isdigit() + join()
res = [''.join(j).strip() for sub in test_list 
        for k, j in groupby(sub, str.isdigit)]

# printing result
print("List after removing stray characters : " + str(res))
```

**Output :**

```
The original list : ['-4', 'Rs 25', '5 kg', '+15']
List after removing stray characters : ['-', '4', 'Rs', '25', '5', 'kg', '+', '15']

```