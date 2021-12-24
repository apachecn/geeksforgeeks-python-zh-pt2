# Python–从列表中删除非英语字符串

> 原文:[https://www . geesforgeks . org/python-remove-非英语-字符-字符串-从列表中删除/](https://www.geeksforgeeks.org/python-remove-non-english-characters-strings-from-list/)

给定一个字符串列表，删除所有非英语字符的字符串。

> **输入** : test_list = ['好|？？？?', '?？极客？？?'】
> **输出** : []
> **解释**:均包含非英文字符
> 
> **输入**:test _ list =【“Gfg”、“Best”】
> **输出**:【“Gfg”、“Best”】
> **解释**:均为有效英文单词。

**方法一:使用正则表达式+ findall() +列表理解**

在这种情况下，我们创建一个 unicode 正则表达式，并检查字符串列表中的出现，使用 findall()提取每个没有 unicode 的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove Non-English characters Strings from List
# Using regex + findall() + list comprehension
import re

# initializing list
test_list = ['Gfg', 'Good| ????', "for",  '??Geeks???']

# printing original list
print("The original list is : " + str(test_list))

# using findall() to neglect unicode of Non-English alphabets
res = [idx for idx in test_list if not re.findall("[^\u0000-\u05C0\u2100-\u214F]+", idx)]

# printing result 
print("The extracted list : " + str(res))
```

**方法 2:使用 regex+search()+filter()+lambda**

在这里，我们只搜索字符串中的英文字母，只提取那些有这些字母的字母。我们使用 filter() + lambda 来执行传递过滤器功能和迭代的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove Non-English characters Strings from List
# Using regex + search() + filter() + lambda
import re

# initializing list
test_list = ['Gfg', 'Good| ????', "for",  '??Geeks???']

# printing original list
print("The original list is : " + str(test_list))

# using search() to get only those strings with alphabets
res = list(filter(lambda ele: re.search("[a-zA-Z\s]+", ele) is not None, test_list))

# printing result 
print("The extracted list : " + str(res))
```