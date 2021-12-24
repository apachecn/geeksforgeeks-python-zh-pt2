# Python–删除 K 后的 N 个字符

> 原文:[https://www . geesforgeks . org/python-remove-n-characters-after-k/](https://www.geeksforgeeks.org/python-remove-n-characters-after-k/)

给定一个字符串，删除 K 字符后的 N 个字符。

> **输入**:test _ str = ' ge @ 987 ekfor @ 123 geeks 最好@212 用于 cs '，N = 3，K = '@'
> **输出**:' geeks forgeks 最好用于 cs'
> **解释**:所有 3 个必选出现被移除。
> 
> **输入**:test _ str = ' geeks for @ 123 geeks 最适合 cs '，N = 3，K = '@'
> **输出** : 'geeksforgeeks 最适合 cs'
> **解释** : @123 被移除。

**方法#1:使用 re.sub()**

在这种情况下，我们指定适当的正则表达式来捕获元素，并从字符串中移除下一个 N 个匹配项。sub()用于执行替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove N characters after K
# Using re.sub()
import re

# initializing strings
test_str = 'geeksfor@123geeks is best@212 for cs'

# printing original string
print("The original string is : " + str(test_str))

# initializing N 
N = 3

# initializing K 
K = '@'

# using re.sub() to perform task 
res = re.sub(r'\@...', '', test_str)

# printing result 
print("The String after removal : " + str(res)) 
```

**Output**

```
The original string is : geeksfor@123geeks is best@212 for cs
The String after removal : geeksforgeeks is best for cs

```

**方法 2:使用 re.sub() +出现选项**

这与上面类似，只是使用 re.sub()的第四个参数来控制我们希望执行替换的出现次数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove N characters after K
# Using re.sub() + occurrence option
import re

# initializing strings
test_str = 'geeksfor@123geeks is best@212 for cs'

# printing original string
print("The original string is : " + str(test_str))

# initializing N 
N = 3

# initializing K 
K = '@'

# using re.sub() to perform task 
# controlling occurrence using 4th arg.
# removes just 1st occurrence
res = re.sub(r'\@...', '', test_str, 1)

# printing result 
print("The String after removal : " + str(res)) 
```

**Output**

```
The original string is : geeksfor@123geeks is best@212 for cs
The String after removal : geeksforgeeks is best@212 for cs

```