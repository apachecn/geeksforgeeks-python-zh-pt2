# Python–从字典字符串值列表中删除数字

> 原文:[https://www . geesforgeks . org/python-从字典中删除数字-字符串-值-列表/](https://www.geeksforgeeks.org/python-remove-digits-from-dictionary-string-values-list/)

给定带有字符串列表值的字典列表，从所有字符串中删除所有数字。

> **输入**:test _ dict = { ' Gfg ':[“G4G 是 Best 4”，“4 ALL 极客”]，' Best ':[“Gfg 天堂”，“为 7 CS”]}
> **输出** : {'Gfg': ['GG 是 Best '，' ALL 极客']，' best': ['Gfg 天堂'，'为 CS']}
> **解释**:删除所有数字串。
> 
> **输入**:test _ dict = { ' Gfg ':[“G4G 是最好的 4”，“4 个 ALL 极客”]}
> **输出** : {'Gfg': ['GG 是最好的'，' ALL 极客']}
> **解释**:去掉所有数字串。

**方法:使用正则表达式+字典理解**

这个问题可以通过两种功能的结合来解决。在本文中，我们使用正则表达式将每个数字替换为空字符串，并使用字典理解来编译结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove digits from Dictionary String Values List
# Using loop + regex() + dictionary comprehension 
import re

# initializing dictionary
test_dict = {'Gfg' : ["G4G is Best 4", "4 ALL geeks"],
             'is' : ["5 6 Good"], 
             'best' : ["Gfg Heaven", "for 7 CS"]} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using dictionary comprehension to go through all keys
res = {key: [re.sub('\d', '', ele) for ele in val]
       for key, val in test_dict.items()}

# printing result 
print("The filtered dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': ['G4G is Best 4', '4 ALL geeks'], 'is': ['5 6 Good'], 'best': ['Gfg Heaven', 'for 7 CS']}
The filtered dictionary : {'Gfg': ['GG is Best ', ' ALL geeks'], 'is': ['  Good'], 'best': ['Gfg Heaven', 'for  CS']}

```