# Python 程序计算字符串中的字数和字符数

> 原文:[https://www . geesforgeks . org/python-计算字符串中单词和字符数量的程序/](https://www.geeksforgeeks.org/python-program-to-calculate-the-number-of-words-and-characters-in-the-string/)

给定一个字符串。任务是找出字符串中出现的单词和字符的数量。

**示例:**

```
Input: Geeksforgeeks is best Computer Science Portal
Output:
The number Of Words are : 6
The Number Of Characters are : 45

Input: Hello World!!!
Output:
The original string is : Hello World!!!
The number of words in string are : 2
The number of words in string are :  14
```

使用 len()函数计算字符串中的字符数。您也可以使用 for 循环来计数字符

```
char=0
for i in string:
    char=char+1
```

用于计数

**方法一:使用** [**分裂()**](https://www.geeksforgeeks.org/python-string-split/)

split 函数非常有用，通常是从列表中取出单词的通用方法，但是一旦我们在列表中引入特殊字符，这种方法就会失败。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to count words in string
# using split()

# initializing string
test_string = "Geeksforgeeks is best Computer Science Portal"

# printing original string
print("The original string is : " + test_string)

# using split()
# to count words in string
res = len(test_string.split())

# printing result
print("The number of words in string are : " + str(res))
print("The number of words in string are : ", len(test_string))
```

**输出:**

> 原字符串为:Geeksforgeeks 是最好的计算机科学门户
> 字符串的字数为:6
> 字符串的字数为:45

**方法 2:** 使用[正则表达式模块](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

这里 findall()函数用于计算正则表达式模块中可用句子的字数。

## 蟒蛇 3

```
import re
test_string = "GeeksForGeeks is a learning platform"

# original string
print("The original string is : " + test_string)

# using regex (findall()) function
res = len(re.findall(r'\w+', test_string))

# total no of words
print("The number of words in string are : " + str(res))
print("The number of Characters in string are : ", len(test_string))
```

**输出:**

> 原字符串为:GeeksForGeeks 是一个学习平台
> 字符串的字数为:5
> 字符串的字符数为:36

**方法 3:** 使用[求和()](https://www.geeksforgeeks.org/sum-function-python/) + [条()](https://www.geeksforgeeks.org/python-string-strip-2/) + [分割()](https://www.geeksforgeeks.org/python-string-split/)功能

这里我们首先检查给定句子中的所有单词，并使用 sum()函数添加它们。

## 蟒蛇 3

```
import string

test_string = "GeeksForGeeks is a learning platform"

# printing original string
print("The original string is: " + test_string)

# using sum() + strip() + split() function
res = sum([i.strip(string.punctuation).isalpha() for i in
           test_string.split()])

# no of words
print("The number of words in string are : " + str(res))
print("The number of characters in string are : ", len(test_string))
```

**输出:**

> 原字符串为:GeeksForGeeks 是一个学习平台
> 字符串的字数为:5
> 字符串的字符数为:36