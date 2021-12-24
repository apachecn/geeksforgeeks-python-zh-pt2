# re。Python 中的 MatchObject.groups()函数–Regex

> 原文:[https://www . geesforgeks . org/re-match object-groups-function-in-python-regex/](https://www.geeksforgeeks.org/re-matchobject-groups-function-in-python-regex/)

此方法返回所有匹配子组的元组。

> **语法:** re。MatchObject.groups()
> 
> **返回:**所有匹配子组的元组
> 
> **属性错误:**如果找不到匹配的模式，则会引发属性错误。

考虑下面的例子:

**例 1:**

## 蟒蛇 3

```py
import re

"""We create a re.MatchObject and store it in 
   match_object variable
   the '()' parenthesis are used to define a 
   specific group"""

match_object = re.match(r'(\d+)\-(\w+)\-(\w+)',
                        '498-ImperialCollege-London')

""" d in above pattern stands for numerical character
    w in above pattern stands for alphabetical character
    + is used to match a consecutive set of characters 
    satisfying a given condition so w+ will match a
    consecutive set of alphabetical characters
    d+ will match a consecutive set of numerical characters
    """

# generating the tuple with all matched groups
detail_tuple = match_object.groups()

# printing the tuple
print(detail_tuple)
```

**输出:**

```py
('498', 'ImperialCollege', 'London')
```

是时候了解上面的程序了。我们使用 **re.match()** 方法来查找给定字符串中的匹配项(**498-imperial college-London**)“**w**”表示我们在搜索字母字符，而“ **+** ”表示我们在给定字符串中搜索连续的字母字符。类似地 **d+** 将匹配一组连续的数字字符。注意使用“ **()** ”括号用于定义不同的子组，在上面的例子中，我们在匹配模式中有三个子组。我们得到的结果是一个 **re。MatchObject** 存储在 match_object 变量中。

**示例 2:** 如果未找到匹配对象，则会引发属性错误。

## 蟒蛇 3

```py
import re

"""We create a re.MatchObject and store it in 
   match_object variable
   the '()' parenthesis are used to define a 
   specific group"""

match_object = re.match(r'(\d+)\-(\w+)\-(\w+)', 
                        '1273984579846')

""" w in above pattern stands for alphabetical character
    + is used to match a consecutive set of characters 
    satisfying a given condition so 'w+' will match a
    consecutive set of alphabetical characters
    """

# Following line will raise AttributeError exception
print(match_object.groups())
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/6510bd3e713a7b9a5629b30325c8a821.py", line 18, in 
    print(match_object.groups())
AttributeError: 'NoneType' object has no attribute 'groups'

```