# Python Regex 中的详细

> 原文:[https://www.geeksforgeeks.org/verbose-in-python-regex/](https://www.geeksforgeeks.org/verbose-in-python-regex/)

在本文中，我们将了解 **re package** 的 **VERBOSE** 标志以及如何使用。

**`re.VERBOSE` :** 该标志允许您编写看起来更好看、更易读的正则表达式，方法是允许您可视化地分隔模式的逻辑部分并添加注释。
模式中的空白被忽略，除非是在字符类中，或者前面有非转义反斜杠，或者在像 `*?, (?: or (?P`这样的标记中。当一行包含不在字符类中的#并且前面没有非转义反斜杠时，从最左边的#到行尾的所有字符都将被忽略。

```
# Without Using VERBOSE
regex_email = re.compile(r'^([a-z0-9_\.-]+)@([0-9a-z\.-]+)\.([a-z\.]{2, 6}){content}apos;,
              re.IGNORECASE)

# Using VERBOSE
regex_email = re.compile(r"""
            ^([a-z0-9_\.-]+)              # local Part
            @                             # single @ sign
            ([0-9a-z\.-]+)                # Domain name
            \.                            # single Dot .
            ([a-z]{2,6}){content}#xA0;                # Top level Domain  
             """,re.VERBOSE | re.IGNORECASE)   
```

它作为参数传递给`re.compile()`，即**重新编译(正则表达式，re。VERBOSE)** 。`re.compile()`返回一个*正则表达式对象*，然后与给定的字符串匹配。

让我们考虑一个例子，用户被要求输入他们的电子邮件标识，我们必须使用正则表达式来验证它。电子邮件的格式如下:

*   个人详细信息/本地部分，如 john123
*   单身@
*   域名，如 gmail/yahoo 等
*   单点(。)
*   顶级域名，如。com/。org/。网

**示例:**

```
Input : expectopatronum@gmail.com
Output : Valid

Input : avadakedavra@yahoo.com@
Output : Invalid
This is invalid because there is @ after the top level domain name.

```

下面是 Python 实现–

```
# Python3 program to show the Implementation of VERBOSE in RegEX
import re

def validate_email(email):

    # RegexObject = re.compile( Regular expression, flag )
    # Compiles a regular expression pattern into 
    # a regular expression object
    regex_email=re.compile(r"""
                           ^([a-z0-9_\.-]+)                 # local Part
                           @                             # single @ sign
                            ([0-9a-z\.-]+)                 # Domain name
                           \.                             # single Dot .
                            ([a-z]{2,6}){content}#xA0;                # Top level Domain     
                           """,re.VERBOSE | re.IGNORECASE)

    # RegexObject is matched with the desired
    # string using fullmatch function
    # In case a match is found, search()
    # returns a MatchObject Instance
    res=regex_email.fullmatch(email)

    #If match is found, the string is valid
    if res:
        print("{} is Valid. Details are as follow:".format(email))

        #prints first part/personal detail of Email Id
        print("Local:{}".format(res.group(1)))

        #prints Domain Name of Email Id
        print("Domain:{}".format(res.group(2)))

        #prints Top Level Domain Name of Email Id
        print("Top Level domain:{}".format(res.group(3)))
        print()

    else:
        #If match is not found,string is invalid
        print("{} is Invalid".format(email))

# Driver Code
validate_email("expectopatronum@gmail.com")
validate_email("avadakedavra@yahoo.com@")
validate_email("Crucio@.com")
```

**输出:**

```
expectopatronum@gmail.com is Valid. Details are as follow:
Local:expectopatronum
Domain:gmail
Top Level domain:com

avadakedavra@yahoo.com@ is Invalid
Crucio@.com is Invalid

```