# 检查密码有效性的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-检查-有效性-密码/](https://www.geeksforgeeks.org/python-program-check-validity-password/)

在这个程序中，我们将把密码作为字母数字字符和特殊字符的组合，并在少数条件的帮助下检查密码是否有效。

**密码验证的主要条件:**

1.  最少 8 个字符。
2.  字母必须在[a-z]之间
3.  至少有一个字母应该大写
4.  [0-9]之间至少有 1 个数字或数字。
5.  [ _ 或@或$ ]中至少有 1 个字符。

示例:

```py
Input : R@m@_f0rtu9e$
Output : Valid Password

Input : Rama_fortune$
Output : Invalid Password
Explanation: Number is missing

Input : Rama#fortu9e 
Output : Invalid Password
Explanation: Must consist from _ or @ or $

```

这里我们使用了 **re** 模块，该模块为 Python 中的[正则表达式提供支持。与此同时，re.search()方法返回 False(如果在第二个参数中找不到第一个参数)，这种方法比提取数据更适合测试正则表达式。我们已经使用 re.search()检查了字母、数字或特殊字符的有效性。为了检查空格，我们使用正则表达式模块中的“\s”。](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

```py
# Python program to check validation of password
# Module of regular expression is used with search()
import re
password = "R@m@_f0rtu9e{content}quot;
flag = 0
while True:  
    if (len(password)<8):
        flag = -1
        break
    elif not re.search("[a-z]", password):
        flag = -1
        break
    elif not re.search("[A-Z]", password):
        flag = -1
        break
    elif not re.search("[0-9]", password):
        flag = -1
        break
    elif not re.search("[_@$]", password):
        flag = -1
        break
    elif re.search("\s", password):
        flag = -1
        break
    else:
        flag = 0
        print("Valid Password")
        break

if flag ==-1:
    print("Not a Valid Password")
```

**Output:**

```py
Valid Password

```

**替代方法:-**

```py
l, u, p, d = 0, 0, 0, 0
s = "R@m@_f0rtu9e{content}quot;
if (len(s) >= 8):
    for i in s:

        # counting lowercase alphabets 
        if (i.islower()):
            l+=1            

        # counting uppercase alphabets
        if (i.isupper()):
            u+=1            

        # counting digits
        if (i.isdigit()):
            d+=1            

        # counting the mentioned special characters
        if(i=='@'or i=='{content}apos; or i=='_'):
            p+=1           
if (l>=1 and u>=1 and p>=1 and d>=1 and l+p+u+d==len(s)):
    print("Valid Password")
else:
    print("Invalid Password")
```

**Output:**

```py
Valid Password

```