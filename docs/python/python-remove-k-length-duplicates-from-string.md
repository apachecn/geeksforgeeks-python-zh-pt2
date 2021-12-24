# Python–从字符串中删除 K 长度的重复项

> 原文:[https://www . geesforgeks . org/python-remove-k-length-duplicates-from-string/](https://www.geeksforgeeks.org/python-remove-k-length-duplicates-from-string/)

给定一个字符串，删除所有长度为 K 的重复项。

> **输入**:test _ str = ' geesforfreeksfo '，K = 3
> **输出**:geesforfree
> **解释** : eek、eks、ksf、sfo 已经在字符串中，因此被移除。
> 
> **输入**:test _ str = ' geesforg '，K = 3
> **输出**:geesforg
> **解释**:无重复串，无删除。

**方法:使用循环+切片**

在这种情况下，我们跟踪遇到的所有 K 长度子串，使用切片提取，并检查每次重复，如果发生，它们被删除。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove K length Duplicates from String
# Using loop + slicing 

# initializing strings
test_str = 'geeksforfreeksfo'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 3

memo = set()
res = []
for idx in range(0, len(test_str) - K):

    # slicing K length substrings
    sub = test_str[idx : idx + K]

    # checking for presence
    if sub not in memo:
        memo.add(sub)
        res.append(sub)

res = ''.join(res[ele] for ele in range(0, len(res), K))

# printing result 
print("The modified string : " + str(res)) 
```

**Output**

```
The original string is : geeksforfreeksfo
The modified string : geeksforfree

```