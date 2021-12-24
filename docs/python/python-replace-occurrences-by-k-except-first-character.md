# Python–用除第一个字符

之外的 K 替换事件

> 原文:[https://www . geesforgeks . org/python-replace-occurs-by-k-except-first-character/](https://www.geeksforgeeks.org/python-replace-occurrences-by-k-except-first-character/)

给定一个字符串，任务是编写一个 Python 程序，用第一个索引处的字符替换第一个索引处的字符。

**示例:**

```
Input : test_str = 'geeksforgeeksforgeeks', K = '@'
Output : geeksfor@eeksfor@eeks

Explanation : All occurrences of g are converted to @ except 0th index.

Input : test_str = 'geeksforgeeks', K = '#'
Output : geeksfor#eeks

Explanation : All occurrences of g are converted to # except 0th index.
```

**方法#1:使用切片+替换()**

在这种情况下，我们执行用出现在第一个索引处的字符的 K 替换第二个字符的整个字符串的任务。结果是前缀由第一个字符连接。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Replace occurrences by K except first character
# Using slicing + replace()

# initializing string
test_str = 'geeksforgeeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = '{content}apos;

# replacing using replace()
res = test_str[0] + test_str[1:].replace(test_str[0], K)

# printing result
print("Replaced String : " + str(res))
```

**输出:**

```
The original string is : geeksforgeeksforgeeks
Replaced String : geeksfor$eeksfor$eeks
```

**方法 2:使用 replace()**

在这种情况下，替换所有出现的任务会调用 replace()两次，然后反向替换第一个出现的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Replace occurrences by K except first character
# Using replace()

# initializing string
test_str = 'geeksforgeeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = '{content}apos;

# replacing using replace()
res = test_str.replace(test_str[0], K).replace(K, test_str[0], 1)

# printing result
print("Replaced String : " + str(res))
```

**输出:**

```
The original string is : geeksforgeeksforgeeks
Replaced String : geeksfor$eeksfor$eeks
```