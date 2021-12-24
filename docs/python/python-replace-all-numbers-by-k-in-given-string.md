# Python–在给定字符串中用 K 替换所有数字

> 原文:[https://www . geesforgeks . org/python-用给定字符串中的 k 替换所有数字/](https://www.geeksforgeeks.org/python-replace-all-numbers-by-k-in-given-string/)

给定一个包含数字的字符串，用 k 替换每个数字

> **输入** : test_str = 'G4G 是 4 全 1 号极客'，K = ' # '
> T3】输出 : G#G 是#全 1 号极客
> T6】解释:所有数字替换为 K
> 
> **输入** : test_str = 'G4G 为 4 全号极客'，K = ' # '
> T3】输出 : G#G 为#全号极客
> **解释**:全号替换为 K

**方法#1:使用 replace() + isdigit()**

在本例中，我们使用 isdigit()检查数字，使用 replace()执行用 k 替换数字的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Replace numbers by K in String
# Using replace() + isdigit()

# initializing string
test_str = 'G4G is 4 all No. 1 Geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = '@'

# loop for all characters
for ele in test_str:
    if ele.isdigit():
        test_str = test_str.replace(ele, K)

# printing result 
print("The resultant string : " + str(test_str)) 
```

**Output**

```py
The original string is : G4G is 4 all No. 1 Geeks
The resultant string : G@G is @ all No. @ Geeks

```

**方法 2:使用 regex() + sub()**

在这种情况下，适当的正则表达式用于识别数字，sub()用于执行替换。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Replace numbers by K in String
# Using regex() + sub()
import re

# initializing string
test_str = 'G4G is 4 all No. 1 Geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = '@'

# using regex expression to solve problem 
res = re.sub(r'\d', K, test_str)

# printing result 
print("The resultant string : " + str(res)) 
```

**Output**

```py
The original string is : G4G is 4 all No. 1 Geeks
The resultant string : G@G is @ all No. @ Geeks

```