# 统计元音周围字符的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-程序-计数-字符-环绕-元音/](https://www.geeksforgeeks.org/python-program-to-count-characters-surrounding-vowels/)

给定一个字符串，任务是编写一个 Python 程序来统计那些以元音为邻的字符。

**示例:**

> **输入**:test _ str = ' geeksforgeicks '
> **输出** : 10
> **解释** : g、k、f、r、g、k、f、r、g、k 有环绕元音。
> 
> **输入** : test_str = 'geeks'
> **输出** : 2
> **解释** : g、k 有环绕元音。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/python-for-loops/)

在这种情况下，我们增加计数器，同时使用循环检查元音的前一个和后一个元素。

## 蟒蛇 3

```py
# initializing string
test_str = 'geeksforgeeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

res = 0
vow_list = ['a', 'e', 'i', 'o', 'u']
for idx in range(1, len(test_str) - 1):

    # checking for preceding and succeeding element to be vowel
    if test_str[idx] not in vow_list and (test_str[idx - 1] in vow_list or test_str[idx + 1] in vow_list):
        res += 1

# solving for 1st and last element
if test_str[0] not in vow_list and test_str[1] in vow_list:
    res += 1

if test_str[-1] not in vow_list and test_str[-2] in vow_list:
    res += 1

# printing result
print("Characters around vowels count : " + str(res))
```

**输出:**

> 原始字符串是:geeksforgeeksforgeeks
> 
> 元音周围的字符数:10

**方法二:** *利用* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/) *和* [*罗列领悟*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在本文中，我们使用 sum()执行获取计数的任务，并使用列表理解完成迭代和过滤。

## 蟒蛇 3

```py
# initializing string
test_str = 'geeksforgeeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

vow_list = ['a', 'e', 'i', 'o', 'u']

# sum() accumulates all vowels surround elements
res = sum([1 for idx in range(1, len(test_str) - 1) if test_str[idx]
           not in vow_list and (test_str[idx - 1] in vow_list or test_str[idx + 1] in vow_list)])

# solving for 1st and last element
if test_str[0] not in vow_list and test_str[1] in vow_list:
    res += 1

if test_str[-1] not in vow_list and test_str[-2] in vow_list:
    res += 1

# printing result
print("Characters around vowels count : " + str(res))
```

**输出:**

> 原始字符串是:geeksforgeeksforgeeks
> 
> 元音周围的字符数:10