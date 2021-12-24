# re。Python 中的 MatchObject.groupdict()函数–Regex

> 原文:[https://www . geesforgeks . org/re-match object-group dict-function-in-python-regex/](https://www.geeksforgeeks.org/re-matchobject-groupdict-function-in-python-regex/)

此方法返回一个字典，其中 groupname 作为键，匹配的字符串作为该键的值。

> **语法:** re。MatchObject.groupdict()
> 
> **返回:**以组名为关键字，匹配字符串为关键字值的字典。
> 
> **属性错误:**如果找不到匹配的模式，则会引发属性错误。

考虑下面的例子:

**例 1:**

一个程序来创建和打印一个详细的字典，包括用户名，网站和域名。

## 蟒蛇 3

```
import re

"""We create a re.MatchObject and store it in 
   match_object variable
   the '()' parenthesis are used to define a 
   specific group"""

match_object = re.match(
    r'(?P<Username>\w+)@(?P<Website>\w+)\.(?P<Domain>\w+)', 'jon@geekforgeeks.org')

""" w in above pattern stands for alphabetical character
    + is used to match a consecutive set of characters 
    satisfying a given condition
    so w+ will match a consecutive set of alphabetical characters
    The ?P<Username> in '()'(the round brackets) is 
    used to capture subgroups of strings satisfying 
    the above condition and the groupname is 
    specified in the ''(angle brackets)in this 
    case its Username."""

# generating a dictionary from the given emailID
details = match_object.groupdict()

# printing the dictionary
print(details)
```

**输出:**

> { '用户名':' jon '，'网站':' geekforgeeks '，' Domain': 'org'}

是时候了解上面的程序了。我们使用 **re.match()** 方法在给定字符串中查找匹配项(**jon@geekforgeeks.org**)“**w**”表示我们在搜索字母字符，而“ **+** ”表示我们在给定字符串中搜索连续的字母字符。注意使用“ **()** ”括号用来定义不同的子组，在上面的例子中，我们在匹配模式中有三个子组。“**？P** 语法用于定义捕获特定组的组名。我们得到的结果是一个 **re。MatchObject** 存储在 match_object 中。

要了解更多关于正则表达式模式的信息，请访问这篇文章。 [Python 正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/amp/)

**示例 2:** 如果未找到匹配对象，则会引发属性错误。

## 蟒蛇 3

```
import re

"""We create a re.MatchObject and store it in 
   match_object variable
   the '()' parenthesis are used to define a 
   specific group"""

match_object = re.match(
    r'(?P<Username>\w+)@(?P<Website>\w+)\.(?P<Domain>\w+)', '1234567890')

""" w in above pattern stands for alphabetical character
    + is used to match a consecutive set of characters 
    satisfying a given condition
    so w+ will match a consecutive set of alphabetical characters
    The ?P<Username> in '()'(the round brackets) is 
    used to capture subgroups of strings satisfying 
    the above condition and the groupname is 
    specified in the ''(angle brackets)in this 
    case its Username."""

# Following line will raise AttributeError exception
print(match_object.groupdict())
```

**输出:**

```
Traceback (most recent call last):
  File "/home/fae2ec2e63d04a63d590c2e93802a002.py", line 21, in 
    print(match_object.groupdict())
AttributeError: 'NoneType' object has no attribute 'groupdict'

```