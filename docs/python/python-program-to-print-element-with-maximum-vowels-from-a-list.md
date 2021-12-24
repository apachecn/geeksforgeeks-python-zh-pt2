# Python 程序打印列表中元音最大的元素

> 原文:[https://www . geesforgeks . org/python-program-to-print-element-with-maximum-from-list/](https://www.geeksforgeeks.org/python-program-to-print-element-with-maximum-vowels-from-a-list/)

给定一个包含字符串元素的列表，任务是编写一个 Python 程序来打印元音最大的字符串。

> **输入**:test _ list =[“gfg”、“best”、“for”、“geeks”]
> **输出** : geeks
> **解释** : geeks 有 2 个 e，这是相对于其他字符串的最大元音数。
> 
> **输入**:test _ list =[“gfg”、“best”]
> **输出** : best
> **解释** : best 有 1 e，这是相对于其他字符串的最大元音数。

**进场:**T2【使用 [*循环*](https://www.geeksforgeeks.org/python-for-loops/)

在这种情况下，我们对所有字符串进行迭代，并保留一个计数器来检查每个字符串中元音的数量。然后，返回循环末尾元音最大的字符串。

## 蟒蛇 3

```
# initializing Matrix
test_list = ["gfg", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

res = ""
max_len = 0
for ele in test_list:

    # getting maximum length and element
    # iteratively
    vow_len = len([el for el in ele if el in ['a', 'e', 'o', 'u', 'i']])
    if vow_len > max_len:
        max_len = vow_len
        res = ele

# printing result
print("Maximum vowels word : " + str(res))
```

**输出:**

> 最初的名单是:['gfg '，' best '，' for '，' geeks']
> 
> 最大元音单词:极客