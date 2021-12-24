# Python–字符串中无 K 的最长连续

> 原文:[https://www . geesforgeks . org/python-最长-连续-不带-k-in-string/](https://www.geeksforgeeks.org/python-longest-consecution-without-k-in-string/)

给定一个字符串，找出最长连续的长度，其中 K 不出现。

> **输入** : test_str = 'geeksforgeeks 最适合极客'，K = 'e'
> **输出** : 9
> **说明**:极客中从 s in best 到 e，第 9 个字母是“e”。
> 
> **输入** : test_str = 'geeksforgeeks '，K = ' e '
> T3】输出 : 7
> **说明**:从 K 到 e，第 7 个字母是 e，最长运行。

**方法#1:使用循环**

我们分两步执行，第一步我们迭代所有元素以获得 K 的索引，然后在下一步找到连续字符之间的最大差异。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Longest Consecution without K in String
# Using loop

# initializing string
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 'e'

# getting all indices 
indxs = []
for idx, ele in enumerate(test_str):
    if ele == 'e':
        indxs.append(idx)

# getting difference 
diffs = []
for idx in range(len(indxs) - 1):
    diffs.append(indxs[idx + 1] - indxs[idx])

# getting max diff using max()
res = max(diffs)

# printing result 
print("Longest run : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks is best for geeks
Longest run : 9

```

**方法 2:使用 filter() + lambda + zip() +列表理解+ max()**

在这种情况下，我们使用 filter() + lambda 和 zip() +获得 K 个元素的索引，列表理解用于获得索引之间的差异。之后，max()用于提取最大差值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Longest Consecution without K in String
# Using filter() + lambda + zip() + list comprehension + max()

# initializing string
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 'e'

# getting all indices using filter + lambda
indxs = list(filter(lambda ele: test_str[ele] == 'e', range(len(test_str)))) 

# getting difference using zip()
# negative index, for getting successive elements 
diffs = [j - i for i, j in zip(indxs[: -1], indxs[1 :])] 

# getting max diff 
res = max(diffs)

# printing result 
print("Longest run : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks is best for geeks
Longest run : 9

```