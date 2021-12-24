# Python 程序从列表值中获取第 k 个索引的最长字母顺序

> 原文:[https://www . geesforgeks . org/python-program-to-get-最长字母顺序-kth-index-from-list-values/](https://www.geeksforgeeks.org/python-program-to-get-the-longest-alphabetic-order-of-kth-index-from-list-values/)

给定一个字符串列表，任务是编写一个 Python 程序来提取在 Kth 索引处形成最长递增字母顺序的字符串。k 应该小于所有字符串的最小长度。

> **输入**:test _ list =[“gfg”、“is”、“best”、“for”、“geeks”、“and”、“cs”]，K = 0
> **输出**:[“best”、“for”、“geeks”]
> **解释**:比较第 0 个索引提取的最长子序列。在第 0 个索引处，b < f < g .最长可能的连续。接下来是“a”变得比“g”小，因此条纹中断。
> 
> **输入**:test _ list =[“gfg”、“is”、“极客”、“and”、“cs”]，K = 0
> **输出**:[“gfg”、“is”]
> **解释**:比较第 0 个索引提取的最长子序列。
> 
> **输入:**test _ list =[“gfg”、“is”、“极客”、“and”、“cs”]，K = 4
> **输出:** []
> **说明:**字符串中最小的长度，是‘is’和‘cs’的 2。因为 K > = min_length，所以没有结果。

**方法:** *使用带滑动窗口的循环*

在这种情况下，我们使用滑动窗口技术不断检查增加的最长子串，并不断更新子串序列的最大值，并更新结果列表。

最后相应地打印结果。

**例**:

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Longest Alphabetic order of Kth index
# Using loop with sliding window

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks", "and", "cs"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

res = []
curr = test_list[:1]
for idx in range(1, len(test_list)):

    # checking for greater element
    if test_list[idx][K] <= test_list[idx - 1][K]:

        # comparing current with maximum length
        if len(curr) > len(res):
            res = curr
        curr = [test_list[idx]]
    else:
        curr.append(test_list[idx])
if len(curr) > len(res):
    res = curr

# printing result
print("Longest increasing Alphabetic order : " + str(res))
```

**输出:**

> 原列表为:['gfg '，' is '，' best '，' for '，' geeks '，' and '，' cs']
> 
> 最长递增字母顺序:['极客'，'和'，' cs']