# Python–子串后缀频率

> 原文:[https://www . geesforgeks . org/python-substring-后缀-frequency/](https://www.geeksforgeeks.org/python-substring-suffix-frequency/)

给定一个字符串和子字符串，计算字符串中可用于完成子字符串的所有替代项。

> **输入**:test _ str =“Gfg 好。Gfg 不错。Gfg 更好。Gfg 不错。”，substr = "Gfg 是"
> **Output** : {'good': 3，' better': 1}
> **解释** : good 作为后缀出现在字符串中的子字符串之后 3 次，因此为 3。等等。
> 
> **输入**:test _ str =“Gfg 好。Gfg 不错。Gfg 不错。Gfg 不错。”，substr = "Gfg 为"
> **输出** : {'good': 4}
> **解释** : good 作为后缀出现在字符串中的子字符串之后 4 次，因此为 4。等等。

**方法#1:使用正则表达式()+ defaultdict() +循环**

这是执行这项任务的方法之一。在本文中，我们构建正则表达式来获取子串的所有匹配元素。然后使用 defaultdict()检查字符串中所有可能出现的频率计数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Substring substitutes frequency
# Using regex() + defaultdict() + loop
from collections import defaultdict
import re

# initializing string
test_str = "Gfg is good . Gfg is best . Gfg is better . Gfg is good ."

# printing original string
print("The original string is : " + str(test_str))

# initializing substring
substr = "Gfg is"

# initializing regex
temp = re.findall(substr + " (\w+)", test_str, flags = re.IGNORECASE)

# adding values to form frequencies
res = defaultdict(int)
for idx in temp:
   res[idx] += 1

# printing result
print("Frequency of replacements : " + str(dict(res)))
```

**Output**

```py
The original string is : Gfg is good . Gfg is best . Gfg is better . Gfg is good .
Frequency of replacements : {'good': 2, 'best': 1, 'better': 1}

```

**方法 2:使用 Counter() + regex()**

这是执行这项任务的另一种方式。在本文中，我们使用 Counter()计算元素频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Substring substitutes frequency
# Using Counter() + regex()
import re
from collections import Counter

# initializing string
test_str = "Gfg is good . Gfg is best . Gfg is better . Gfg is good ."

# printing original string
print("The original string is : " + str(test_str))

# initializing substring
substr = "Gfg is"

# initializing regex
temp = re.findall(substr + " (\w+)", test_str, flags = re.IGNORECASE)

# adding values to form frequencies
res = dict(Counter(temp))

# printing result
print("Frequency of replacements : " + str(res))
```

**Output**

```py
The original string is : Gfg is good . Gfg is best . Gfg is better . Gfg is good .
Frequency of replacements : {'good': 2, 'best': 1, 'better': 1}

```