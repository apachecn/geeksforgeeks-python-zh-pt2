# re。Python Regex 中的 MatchObject.group()函数

> 原文:[https://www . geesforgeks . org/re-match object-group-function-in-python-regex/](https://www.geeksforgeeks.org/re-matchobject-group-function-in-python-regex/)

**re。MatchObject.group()** 方法默认返回完整的匹配子组，或者根据参数的数量返回匹配子组的元组

> **语法:** re。MatchObject.group([group])
> 
> **参数:**
> 
> *   **组:(可选)** *组*默认为零(意味着它将返回完整的匹配字符串)。返回-1 如果*组*存在但没有为比赛做出贡献。
> 
> **返回:**默认情况下完成匹配，否则根据参数选择一个或多个匹配的子组。
> 
> **索引错误:**如果作为参数传递的组号为负数或大于匹配模式中定义的组号，则将引发索引错误异常
> 
> **属性错误:**如果找不到匹配的模式，则会引发属性错误。

考虑下面的例子:

**例 1:**

从电子邮件中打印用户名、公司名和域名的程序

## 蟒蛇 3

```py
import re

"""We create a re.MatchObject and store it in
   match_object variable
   the '()' parenthesis are used to define a
   specific group"""

match_object = re.match(r'(\w+)@(\w+)\.(\w+)', 'username@geekforgeeks.org')

""" w in above pattern stands for alphabetical character
    + is used to match a consecutive set of characters
    satisfying a given condition
    so w+ will match a consecutive set of alphabetical characters"""

# for entire match
print(match_object.group())
# also print(match_object.group(0)) can be used

# for the first parenthesized subgroup
print(match_object.group(1))

# for the second parenthesized subgroup
print(match_object.group(2))

# for the third parenthesized subgroup
print(match_object.group(3))

# for a tuple of all matched subgroups
print(match_object.group(1, 2, 3))
```

**输出:**

```py
username@geekforgeeks.org
username
geekforgeeks
org
('username', 'geekforgeeks', 'org')
```

是时候了解上面的程序了。我们使用 **re.match()** 方法在给定字符串中查找匹配项(**username@geekforgeeks.org**)“**w**”表示我们在搜索字母字符，而“ **+** ”表示我们在给定字符串中搜索连续的字母字符。注意使用“ **()** ”括号用来定义不同的子组，在上面的例子中，我们在匹配模式中有三个子组。我们得到的结果是一个 **re。MatchObject** 存储在 match_object 中。

**注意:**要了解更多正则表达式模式，请参考 [Python 正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/amp/)

根据传递的参数，group 方法返回不同的字符串，并且还返回匹配字符串的元组。

**例 2:**

如果我们在方法参数中传递一个无效的组号，那么我们将得到一个 IndexError 异常。

## 蟒蛇 3

```py
import re

"""We create a re.MatchObject and store it in
   match_object variable
   the '()' parenthesis are used to define a
   specific group"""

match_object = re.match(r'(\w+)@(\w+)\.(\w+)', 'username@geekforgeeks.org')

""" w in above pattern stands for alphabetical character
    + is used to match a consecutive set of characters
    satisfying a given condition
    so w+ will match a consecutive set of alphabetical characters"""

# Following line will raise IndexError exception
print(match_object.group(7))
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/8da42759204c98da7baa88422a4a74e0.py", line 17, in 
    print(match_object.group(7))
IndexError: no such group
```