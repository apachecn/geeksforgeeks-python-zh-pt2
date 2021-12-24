# Python–对由分隔符分隔的单词进行排序

> 原文:[https://www . geesforgeks . org/python-sort-words-用分隔符分隔/](https://www.geeksforgeeks.org/python-sort-words-separated-by-delimiter/)

给定的由某种分隔符分隔的单词串。任务是对字符串

```
Input : test_str = 'gfg:is:best:for:geeks', delim = "*" 
Output : best*for*geeks*gfg*is 
Explanation : Words sorted after separated by delim.

Input : test_str = 'gfg:is:best', delim = "*" 
Output : best*gfg*is 
Explanation : Words sorted after separated by delim. 
```

中给出的所有单词进行排序

**方法:使用排序()+连接()+拆分()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 通过特定的分隔符分隔所有单词，并转换为列表，然后执行单词排序，然后重新转换为由相同分隔符附加的字符串。

T5】蟒 3T7

```
# Python3 code to demonstrate working of
# Sort words separated by Delimiter
# Using split() + join() + sorted()

# initializing string
test_str = 'gfg:is:best:for:geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing Delimiter
delim = ":"

# joining the sorted string after split
res = delim.join(sorted(test_str.split(':')))

# printing result
print("The sorted words : " + str(res))
```

T8T10**输出**T1