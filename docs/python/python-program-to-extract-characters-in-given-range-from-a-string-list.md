# 从字符串列表中提取给定范围内字符的 Python 程序

> 原文:[https://www . geesforgeks . org/python-从字符串列表中提取给定范围内字符的程序/](https://www.geeksforgeeks.org/python-program-to-extract-characters-in-given-range-from-a-string-list/)

给定一个字符串列表，提取跨越整个字符串列表的索引范围内的字符。

> **输入**:test _ list =[“geeks forgeeks”，“is”，“best”，“for”，“geeks”]，strt，end = 14，20
> **输出** : sbest
> **解释**:一旦串接，提取 14–20 范围。
> 
> **输入**:test _ list =[“geeks forgeeks”“is”“best”“for”“geeks”]，strt，end = 11，20
> T3】输出 : sbesbest
> **解释**:一旦串接，提取 11–20 范围。

**方法一:使用 join() +列表理解**

在这种情况下，我们使用[连接()](https://www.geeksforgeeks.org/join-function-python/#:~:text=The%20join()%20method%20is,of%20iterable%20will%20be%20stored.)和[列表理解](https://www.geeksforgeeks.org/comprehensions-in-python/)来执行所有字符串的连接，然后提取所需的字符范围。

## 蟒蛇 3

```
# initializing list
test_list = ["geeksforgeeks", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing char range 
strt, end = 14, 30

# strt and end used to get desired characters
res = ''.join([sub for sub in test_list])[strt : end]

# printing result 
print("Range characters : " + str(res))
```

**Output**

```
The original list is : ['geeksforgeeks', 'is', 'best', 'for', 'geeks']
Range characters : sbestforgeeks

```

**方法 2:使用 chain . from _ iterable()+join()**

在本例中，我们使用 [chain.from_iterable()](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/#:~:text=from_iterable()%20method,elements%20of%20the%20input%20iterable.) 执行字符展平任务，然后使用 join()连接所有字符串，并在范围内提取索引。

## 蟒蛇 3

```
# import module
from itertools import chain

# initializing list
test_list = ["geeksforgeeks", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing char range 
strt, end = 14, 30

# strt and end used to get desired characters
res = ''.join(chain.from_iterable(test_list))[strt : end]

# printing result 
print("Range characters : " + str(res))
```

**Output**

```
The original list is : ['geeksforgeeks', 'is', 'best', 'for', 'geeks']
Range characters : sbestforgeeks

```