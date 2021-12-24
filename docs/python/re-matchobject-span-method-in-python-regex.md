# re。Python 中的 MatchObject.span()方法–正则表达式

> 原文:[https://www . geesforgeks . org/re-match object-span-method in-python-regex/](https://www.geeksforgeeks.org/re-matchobject-span-method-in-python-regex/)

re。MatchObject.span()方法返回包含匹配字符串的起始和结束索引的元组。如果组对匹配没有贡献，则返回(-1，-1)。

> **语法:** re。MatchObject.span()
> 
> **参数:** *组* **(可选)**默认为 0。
> 
> **返回:**包含匹配字符串的起始和结束索引的元组。如果组对匹配没有贡献，则返回(-1，-1)。
> 
> **属性错误:**如果没有找到匹配的模式，则会引发属性错误。

考虑下面的例子:

**例 1:**

## 蟒蛇 3

```py
# import library
import re

"""
We create a re.MatchObject and 
store it in  match_object variable, 
'()' parenthesis are used to define a 
specific group
"""
match_object = re.match(r'(\d+)',
                        '128935')

""" 
d in above pattern stands for numerical character
+ is used to match a consecutive set of characters 
satisfying a given condition so d+ will match a
consecutive set of numerical characters
"""

# generating the tuple with the 
# starting and ending index
print(match_object.span())
```

**输出:**

```py
(0, 6)    

```

是时候了解上面的程序了。我们使用 **re.match()** 方法在给定字符串中查找匹配项(**128935**)“**d**”表示我们正在搜索数字字符，而“ **+** ”表示我们正在给定字符串中搜索连续的数字字符。**注**使用“ **()** ”括号用于定义不同的子组。

**示例 2:** 如果未找到匹配对象，则会引发属性错误。

## 蟒蛇 3

```py
# import library
import re

"""
We create a re.MatchObject and 
store it in match_object variable,
'()' parenthesis are used to define a 
specific group"""

match_object = re.match(r'(\d+)',
                        'geeks')

""" 
d in above pattern stands for numerical character
+ is used to match a consecutive set of characters 
 satisfying a given condition so d+ will match a
consecutive set of numerical characters
"""

# generating the tuple with the
# starting and ending index
print(match_object.span())
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/18a058de83529572f8d50dc9f8bbd34b.py", line 17, in 
    print(match_object.span())
AttributeError: 'NoneType' object has no attribute 'span'

```