# Python 程序连接字符串的第 Kth 个索引字

> 原文:[https://www . geesforgeks . org/python-program-to-concatenate-kth-index-word-of-string/](https://www.geeksforgeeks.org/python-program-to-concatenate-kth-index-words-of-string/)

给定一个包含单词的字符串，连接每个单词的 Kth 索引。

> **输入**:test _ str = ' geeks forgeeks best geeks '，K = 3
> **输出** : ktk
> **说明**:“geeks forgeeks”的第 3 个索引为 K，“best”有‘t’作为第 3 个元素。
> 
> **输入**:test _ str = ' geeks forgeeks best geeks '，K = 0
> T3】输出 : gbg

**方法一:使用 join() +列表理解+ split()**

在这种情况下，我们执行拆分任务以获得所有单词，然后使用列表理解来获得单词的所有 Kth 索引，join()用于执行串联。

## 蟒蛇 3

```py
# initializing string
test_str = 'geeksforgeeks best for geeks'

# printing original string
print("The original string is : " + test_str)

# initializing K 
K = 2

# joining Kth index of each word
res = ''.join([sub[K] for sub in test_str.split()])

# printing result 
print("The K joined String is : " + str(res))
```

**输出:**

```py
The original string is : geeksforgeeks best for geeks
The K joined String is : esre

```

**方法 2:使用循环+连接()**

在本文中，我们以强力方式使用循环来执行获取 Kth 索引元素的任务，然后使用 join()进行连接。

## 蟒蛇 3

```py
# initializing string
test_str = 'geeksforgeeks best for geeks'

# printing original string
print("The original string is : " + test_str)

# initializing K 
K = 2

# getting Kth element of each word
temp = []
for sub in test_str.split():
  temp.append(sub[K])

# joining together  
res = ''.join(temp)

# printing result 
print("The K joined String is : " + str(res))
```

**输出:**

```py
The original string is : geeksforgeeks best for geeks
The K joined String is : esre

```