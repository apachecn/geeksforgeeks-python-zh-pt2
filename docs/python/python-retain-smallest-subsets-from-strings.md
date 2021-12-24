# Python–保留字符串中最小的子集

> 原文:[https://www . geesforgeks . org/python-retain-minist-subset-from-strings/](https://www.geeksforgeeks.org/python-retain-smallest-subsets-from-strings/)

给定一组字符串，任务是编写一个 python 程序，从找到的最小可能的字符串子集集中保留字符串。

> **输入:** test_set = {'cbabca '，' cba '，' bdb '，' bdbab '，' abcx'}
> 
> **输出:**{‘BDB’，‘ABCD’，‘CBA’}
> 
> **解释:** bdbab 被移除，因为 bdb(较小的子集)被保留。
> 
> **输入:** test_set = {'cbabca '，' cba '，' bdbab '，' abcx'}
> 
> **输出:** {'bdbab '，' abcx '，' cba'}
> 
> **解释:**cba ca 被移除，因为 CBA(较小的子集)被保留。

**方法:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/) **+** [**任意()**](https://www.geeksforgeeks.org/python-any-function/) **+** [**串切片**](https://www.geeksforgeeks.org/string-slicing-in-python/)

在这种情况下，我们通过对子字符串集进行排序来执行获取最小子字符串的任务，并使用 any()来测试是否有任何子集与作为小于当前字符串的结果提取的字符串中存在的字符串子字符串以及字符串的子集相匹配。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Retain smallest subsets from string
# Using sorted() + any() + string slicing

# initializing strings set
test_set = {'cbabca', 'cba', 'bdb', 'bdbab', 'abcx'}

# printing original string
print("The original set is : " + str(test_set))

res = set()
for st_r in sorted(test_set, key=len):

    # getting smallest set and checking for already 
    # present smaller set for subset
    if not any(st_r[idx: idx + y + 1] in res 
               for idx in range(len(st_r)) 
               for y in range(len(st_r) - idx)):
        res.add(st_r)

# printing result
print("Required extracted strings : " + str(res))
```

**输出:**

```
The original set is : {'cba', 'abcx', 'bdb', 'bdbab', 'cbabca'}
Required extracted strings : {'abcx', 'cba', 'bdb'}
```