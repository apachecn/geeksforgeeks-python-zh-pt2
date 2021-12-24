# Python–下标词典

> 原文:[https://www.geeksforgeeks.org/python-subscript-dictionary/](https://www.geeksforgeeks.org/python-subscript-dictionary/)

有时候，在 Python 中处理数据时，我们会遇到一个问题，那就是我们需要使用下标版本的数字，而不是普通的数字。为此，拥有一个将数字与其下标版本进行映射的字典有很好的实用性。让我们讨论执行这项任务的某些方法。

> **输入:** test_str = "012345"
> **输出:** {'0 ':？', '1': '?', '2': '?', '3': '?', '4': '?', '5': '?'}
> 
> **输入:**test _ str = " 0 "
> T3】输出: {'0 ':？'}

**方法#1:使用 loop+order()**
这是我们执行这个任务的蛮力方式。在本文中，我们遍历需要下标的数字，并使用 order()及其二进制值构造下标值。在 Python 3.7 +中工作。

```py
# Python3 code to demonstrate working of 
# Subscript Dictionary
# Using loop + ord()

# initializing string
test_str = "0123456789"

# printing original string
print("The original string is : " + test_str)

# initializing Subscript number value
K = u'\u2080'

# Subscript Dictionary
# Using loop + ord()
res = {}
for ele in test_str:
    res[ele] = K
    K = chr(ord(K) + 1)

# printing result 
print("The split string is : " + str(res)) 
```

**Output :**

> 原字符串为:0123456789
> 拆分字符串为:{'7 ':？', '4': '?', '2': '?', '3': '?', '5': '?', '8': '?', '1': '?', '6': '?', '0': '?', '9': '?'}

**方法 2:使用字典理解**
这是执行这项任务的另一种方式。在这种情况下，我们执行与上面类似的任务，只是使用一行中的理解。在 Python 3.7 +中工作。

```py
# Python3 code to demonstrate working of 
# Subscript Dictionary
# Using Dictionary comprehension

# initializing string
test_str = "0123456789"

# printing original string
print("The original string is : " + test_str)

# initializing Subscript number value
K = u'\u2080'

# Subscript Dictionary
# Using Dictionary comprehension
res = {ele : chr(ord(K) + 1) for ele in test_str}

# printing result 
print("The split string is : " + str(res)) 
```

**Output :**

> 原字符串为:0123456789
> 拆分字符串为:{'7 ':？', '4': '?', '2': '?', '3': '?', '5': '?', '8': '?', '1': '?', '6': '?', '0': '?', '9': '?'}