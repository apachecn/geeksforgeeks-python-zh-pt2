# Python |以不同方式拆分字符串的方法

> 原文:[https://www . geesforgeks . org/python-不同方式拆分字符串的方法/](https://www.geeksforgeeks.org/python-ways-to-split-a-string-in-different-ways/)

我们在 Python 中遇到的最常见的问题是用分隔符拆分字符串，但是在某些情况下，我们必须以不同的方式进行拆分才能得到答案。在本文中，我们将通过不同的方式拆分字符串来获得子字符串。

**示例:**

> **输入:** Paras_Jain_Moengage_best
> 输出: ['Paras '，' Paras_Jain '，' Paras_Jain_Moengage '，' Paras_Jain_Moengage_best']
> 
> **输入:**chunky_2808 _ GFG _ Codechef
> T3】输出: ['chunky '，' chunky _ 2808 '，' chunky_2808_GFG '，' chunky_2808_GFG_Codechef']

下面是一些完成任务的方法。

**方法#1:使用迭代**

```py
# Python code to split string in substring manner

# Input initialisation
Input = "Geeks_for_geeks_is_best"

# Split initialise
split_string = Input.split('_')

# Output list initialise
Output = []

# Iteration
for a in range(len(split_string)):
    temp = split_string[:a + 1]
    temp = "_".join(temp)
    Output.append(temp)

# print output
print(Output)
```

**Output:**

> ['极客'，'极客 _for '，'极客 _ for _ 极客'，'极客 _ for _ 极客 _is '，'极客 _ for _ 极客 _is_best']

**方法 2:使用 Itertools**

```py
# Python code to split string in substring manner

# Importing 
from itertools import accumulate

# Input initialisation
Input = "Geeks_for_geeks_is_best"

# Using accumulate
Output = [*accumulate(Input.split('_'), lambda temp1, temp2 :
                                   '_'.join([temp1, temp2])), ]

# Printing output
print(Output)
```

**Output:**

> ['极客'，'极客 _for '，'极客 _ for _ 极客'，'极客 _ for _ 极客 _is '，'极客 _ for _ 极客 _is_best']