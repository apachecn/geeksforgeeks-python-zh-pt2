# Python–用 I 替换 Consonents，用 j 替换元音

> 原文:[https://www . geesforgeks . org/python-replace-consonents-by-I-元音-by-j/](https://www.geeksforgeeks.org/python-replace-consonents-by-i-vowels-by-j/)

给定一个字符串，用 I 替换所有的元音，用 j 替换所有的辅音

> **输入** : test_str = 'geeksforgeeks '，I，j = ' A "，" B"
> **输出**:baababbaabb
> **解释**:所有元音由 A 替换，同音由 B 替换。
> 
> **输入** : test_str = 'gfg '，I，j = ' A "，" B"
> **输出** : BBB
> **解释**:只有同宗者在场，被 B 替换

**方法#1:使用 sub() +正则表达式**

在这种情况下，我们使用 sub 函数，并通过正则表达式对同音和元音进行适当的替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace Consonents by i, Vowels by j
# Using Using sub() + regex
import re

# initializing strings
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing i, j
i, j = "V", "C"

# the negation of vowel regex is a consonent, denoted by "^"
res = re.sub("[^aeiouAEIOU]", j, test_str)
res = re.sub("[aeiouAEIOU]", i, res)

# printing result 
print("The string after required replacement : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The string after required replacement : CVVCCCVCCVVCC

```

**方法 2:使用 maketrans() +对称差分**

在本文中，我们首先利用元音的对称差和 maketrans is 函数得到了用于执行字符串替换任务的概念。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace Consonents by i, Vowels by j
# Using maketrans() + symmetric difference
import string

# initializing strings
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing i, j
i, j = "V", "C"

# extracting voweks and consonents
Vows = 'aeiouAEIOU'

# using sym. diff to get consonents
Cons = ''.join(set(string.ascii_letters).difference(set(Vows)))

# initializing translation
translation = str.maketrans(Vows + Cons, i * len(Vows) + j * len(Cons))

res = test_str.translate(translation)

# printing result 
print("The string after required replacement : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The string after required replacement : CVVCCCVCCVVCC

```