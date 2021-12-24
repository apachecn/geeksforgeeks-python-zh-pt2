# 不使用内置函数计算大小写字符的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-count-大写-小写-字符-不使用内置函数/](https://www.geeksforgeeks.org/python-program-count-upper-lower-case-characters-without-using-inbuilt-functions/)

给定一个包含大写和小写字符的字符串。任务是在不使用内置函数的情况下计算其中大写和小写字符的数量。

使用`isupper()`和`islower()`功能可以很容易的计算出一个字符串的大小写字符，参见[这个](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/)。但是在没有任何内置功能帮助的情况下做同样的事情是非常令人兴奋的。让我们看看如何做到这一点:

示例:

```
Input : Introduction to Python
Output : Lower Case characters : 18 Upper case characters : 2

Input :  Welcome to GeeksforGeeks
Output : Lower Case characters : 19  Upper case characters: 3

```

以下是上述思路的实现:

```
# Python3 program to count upper and
# lower case characters without using
# inbuilt functions
def upperlower(string):

    upper = 0
    lower = 0

    for i in range(len(string)):

        # For lower letters
        if (ord(string[i]) >= 97 and
            ord(string[i]) <= 122):
            lower += 1

        # For upper letters
        elif (ord(string[i]) >= 65 and
              ord(string[i]) <= 90):
            upper += 1

    print('Lower case characters = %s' %lower,
          'Upper case characters = %s' %upper)

# Driver Code
string = 'GeeksforGeeks is a portal for Geeks'
upperlower(string)
```

**Output:**

```
Lower case characters = 27 Upper case characters = 3

```

**替代方法:-**

```
s = "The Geek King"
l,u = 0,0
for i in s:
    if (i>='a'and i<='z'):

        # counting lower case
        l=l+1                 
    if (i>='A'and i<='Z'):

        #counting upper case
        u=u+1   

print('Lower case characters: ',l)
print('Upper case characters: ',u)
```

**Output:**

```
Lower case characters:  8
Upper case characters:  3

```