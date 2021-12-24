# Python |检查字符串是否包含所有相同字符的方法

> 原文:[https://www . geesforgeks . org/python-检查字符串的方法-包含所有相同的字符/](https://www.geeksforgeeks.org/python-ways-to-check-string-contain-all-same-characters/)

给定一个字符串列表，编写一个 Python 程序来检查每个字符串是否都有相同的字符。下面给出了几个检查相同的方法。

**方法#1:使用天真法**【低效】

```
# Python code to demonstrate 
# to check whether string contains
# all characters same or not

# Initialising string list
ini_list = ["aaaaaaaaaaa", "aaaaaaabaa"]

# Printing initial string
print ("Initial Strings list", ini_list)

# Using Naive Method:
flag = True
for i in ini_list:
    for j in range(0, len(i)-1):
        if i[j]!= i[j + 1]:
            print ("String {} don't have all characters same".format(i))
            flag = False
            break
    if flag == True:
        print ("String {} don't have all characters same".format(i))

```

**输出:**

```
Initial Strings list ['aaaaaaaaaaa', 'aaaaaaabaa']
String aaaaaaaaaaa don't have all characters same
String aaaaaaabaa don't have all characters same

```