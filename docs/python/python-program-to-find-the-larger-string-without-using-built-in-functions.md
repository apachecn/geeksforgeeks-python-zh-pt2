# 不使用内置函数寻找较大字符串的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-the-big-string-无需使用内置函数/](https://www.geeksforgeeks.org/python-program-to-find-the-larger-string-without-using-built-in-functions/)

给定两个字符串。任务是在不使用内置函数的情况下找到较大的字符串。

**例:**

```py
Input:
GeeksforGeeks
Geeks
Output:
GeeksforGeeks

Input:
GeeksForFeeks is an good Computer Coding Website
It offers several topics
Output:
GeeksForFeeks is an good Computer Coding Website

```

**分步方法:**

*   在单独的变量中取两个字符串。
*   将两个计数变量初始化为零。
*   使用 for 循环遍历字符串中的字符，并在每次遇到字符时递增计数变量。
*   比较两个字符串的计数变量。
*   打印较大的字符串。
*   出口。

**以下是基于上述方法的完整程序:**

## python 3

```py
string1="GeeksForFeeks is an good Computer Coding Website "
string2="It offers several topics"
count1=0
count2=0

for i in string1:
      count1=count1+1
for j in string2:
      count2=count2+1

if(count1<count2):
      print("Larger string is:")
      print(string2)

elif(count1==count2):
      print("Both strings are equal.")

else:
      print("Larger string is:")
      print(string1)
```

**输出**

```py
Larger string is:
GeeksForFeeks is an good Computer Coding Website 

```

**程序说明:**

1.  The user must enter two strings and store them in separate variables.
2.  The variable is initialized to zero.
3.  The for loop is used to iterate through the characters in the string.
4.  Every time a character is encountered, the counting variable is incremented.
5.  Then compare the count variables and print a larger string.