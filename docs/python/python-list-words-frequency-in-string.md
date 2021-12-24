# Python–在字符串中列出单词频率

> 原文:[https://www . geesforgeks . org/python-list-words-frequency-in-string/](https://www.geeksforgeeks.org/python-list-words-frequency-in-string/)

给定一个单词列表，将每个单词的出现频率映射到字符串中。

> **输入** : test_str = 'geeksforgeeks 最适合极客，最适合 CS '，count_list = ['best '，' geeksforgeeks '，' computer']
> **输出**:【2，1，0】
> **解释** : best 有 2 个 occ。geeksforgeeks 1 和计算机不在字符串中。
> **输入** : test_str = 'geeksforgeeks 最适合 geeks，最适合 CS '，count_list = ['better '，' gfg '，' computer']
> **输出** : [0，0，0]
> **解释**:字符串中没有列表中的单词。

**方法一:使用 defaultdict() +循环+列表理解**

在这种情况下，我们使用 loop + defaultdict()计算单词频率，然后使用列表理解来获得与单词列表相对应的所有计数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Divide String into Equal K chunks
# Using list comprehension
from collections import defaultdict

# initializing strings
test_str = 'geeksforgeeks is best for geeks and best for CS'

# printing original string
print("The original string is : " + str(test_str))

# initializing count_list
count_list = ['best', 'geeksforgeeks', 'computer', 'better', 'for', 'and']

# computing frequency
res = defaultdict(int)
for sub in test_str.split():
    res[sub] += 1

# assigning to list words
res = [res[sub] for sub in count_list]

# printing result
print("The list words frequency : " + str(res))
```

**Output**

```
The original string is : geeksforgeeks is best for geeks and best for CS
The list words frequency : [2, 1, 0, 0, 2, 1]
```

**方法二:使用 Counter() +列表理解**

在这种情况下，Counter()用于执行计算频率的任务，也就是说，列表理解用于为列表单词分配频率。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Divide String into Equal K chunks
# Using list comprehension
from collections import Counter

# initializing strings
test_str = 'geeksforgeeks is best for geeks and best for CS'

# printing original string
print("The original string is : " + str(test_str))

# initializing count_list
count_list = ['best', 'geeksforgeeks', 'computer', 'better', 'for', 'and']

# computing frequency using Counter()
res = Counter(test_str.split())

# assigning to list words
res = [res[sub] for sub in count_list]

# printing result
print("The list words frequency : " + str(res))
```

**Output**

```
The original string is : geeksforgeeks is best for geeks and best for CS
The list words frequency : [2, 1, 0, 0, 2, 1]
```