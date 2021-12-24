# 从其他列表中提取至少具有给定字符数的字符串的 Python 程序

> 原文:[https://www . geesforgeks . org/python-从其他列表中提取至少给定字符数的字符串的程序/](https://www.geeksforgeeks.org/python-program-to-extract-strings-with-at-least-given-number-of-characters-from-other-list/)

给定一个只包含字符串元素的列表，任务是编写一个 Python 程序，从给定次数的另一个列表中提取所有包含字符的字符串。

**示例:**

> **输入**:test _ list =[“geeks forgeeks”，“is”，“best”，“for”，“geeks”]，char_list = ['e '，' t '，' s '，' m '，' n']，K = 2
> 
> **输出:** ['极客 forgeeks '，'最佳'，'极客']
> 
> **说明:**为有 1，为列表中有 0 个字符，故省略。
> 
> **输入:**test _ list =[“geeks forgeeks”，“is”，“best”，“for”，“geeks”]，char_list = ['t '，' s '，' m '，' n']，K = 2
> 
> **输出:** ['Geeksforgeeks '，' best']
> 
> **说明:** Geeksforgeeks 有 2 s，最好有人物列表中的 2 个元素。

**方法一:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/)

在这种情况下，我们使用列表理解来执行字符的迭代，并且 sum()用于检查匹配的字符 sum，如果发现其大于 K，则将其添加到结果列表中。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = ["Geeksforgeeks", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing characters list
char_list = ['e', 't', 's', 'm', 'n']

# initializing K
K = 2

# sum() computes matching elements frequency
res = [ele for ele in test_list if sum(ch in char_list for ch in ele) >= K]

# printing result
print("Filtered Strings : " + str(res))
```

**输出:**

> 最初的名单是:[‘极客’，‘是’，‘最好’，‘适合’，‘极客’
> 
> 过滤字符串:[“极客”、“最佳”、“极客”]

**方法二:** *使用* [*滤镜()*](https://www.geeksforgeeks.org/filter-in-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*和* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/)*

*在这种情况下，使用 filter()执行过滤任务，其余所有功能使用与上述方法类似的构造来执行。*

***程序:***

## *蟒蛇 3*

```py
*# initializing list
test_list = ["Geeksforgeeks", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing characters list
char_list = ['e', 't', 's', 'm', 'n']

# initializing K
K = 2

# sum() computes matching elements frequency
# filter() used for task of filtering
res = list(filter(lambda ele: sum(ch in char_list for ch in ele) >= K, test_list))

# printing result
print("Filtered Strings : " + str(res))*
```

***输出:***

> *最初的名单是:[‘极客’，‘是’，‘最好’，‘适合’，‘极客’*
> 
> *过滤字符串:[“极客”、“最佳”、“极客”]*