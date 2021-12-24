# Python–一次替换字符串中的不同字符

> 原文:[https://www . geesforgeks . org/python-一次替换不同的字符串字符/](https://www.geeksforgeeks.org/python-replace-different-characters-in-string-at-once/)

给定要用相应值替换的字符的映射，在一行中一次执行所有替换。

> **输入** : test_str = 'geeksforgeeks 最好'，map_dict = {'e':'1 '，' b ':' 6 ' }
> **输出** : g11ksforg11ks 为第 61 位
> **解释**:所有 e 用 1 代替，b 用 6 代替。
> **输入** : test_str = 'geeksforgeeks '，map_dict = {'e':'1 '，' b ':' 6 ' }
> **输出** : g11ksforg11ks
> **解释**:所有 e 都被 1 代替，b 被 6 代替。

**方法#1:使用 join() +生成器表达式**

在这种情况下，我们执行获取字典中存在的字符的任务，并通过字典访问将它们映射到它们的值，所有其他字符不变地被追加，结果使用 join()转换回字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace Different characters in String at Once
# using join() + generator expression

# initializing string
test_str = 'geeksforgeeks is best'

# printing original String
print("The original string is : " + str(test_str))

# initializing mapping dictionary
map_dict = {'e':'1', 'b':'6', 'i':'4'}

# generator expression to construct vals
# join to get string
res = ''.join(idx if idx not in map_dict else map_dict[idx] for idx in test_str)

# printing result
print("The converted string : " + str(res))
```

**Output**

```py
The original string is : geeksforgeeks is best
The converted string : g11ksforg11ks 4s 61st
```

**方法 2:使用正则表达式+λ**

这是处理问题的复杂方法。在这种情况下，我们使用 lambda 函数构造适当的正则表达式，并执行所需的替换任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace Different characters in String at Once
# using regex + lambda
import re

# initializing string
test_str = 'geeksforgeeks is best'

# printing original String
print("The original string is : " + str(test_str))

# initializing mapping dictionary
map_dict = {'e':'1', 'b':'6', 'i':'4'}

# using lambda and regex functions to achieve task
res = re.compile("|".join(map_dict.keys())).sub(lambda ele: map_dict[re.escape(ele.group(0))], test_str)

# printing result
print("The converted string : " + str(res))
```

**Output**

```py
The original string is : geeksforgeeks is best
The converted string : g11ksforg11ks 4s 61st
```