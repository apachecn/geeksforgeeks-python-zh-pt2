# Python 中从字符串中删除第 I 个字符的方法

> 原文:[https://www . geesforgeks . org/从 python 字符串中移除字符的方法/](https://www.geeksforgeeks.org/ways-to-remove-ith-character-from-string-in-python/)

在 Python 中，众所周知，字符串是不可变的，因此在编写日常编程所需的结构时，有时会造成可见的限制。本文提出了一个从字符串中删除第 I 个字符的问题，并讨论了实现这些问题的可能解决方案。

**Method 1 : Naive Method**

在这种方法中，除了当索引为 I 时，只需要运行一个循环并在字符出现时追加它们，然后从现有的字符串构建一个新的字符串。

**代码#1 :** 演示从字符串中移除第一个字符的简单方法。

```
# Python code to demonstrate
# method to remove i'th character
# Naive Method

# Initializing String 
test_str = "GeeksForGeeks"

# Printing original string 
print ("The original string is : " + test_str)

# Removing char at pos 3
# using loop
new_str = ""

for i in range(len(test_str)):
    if i != 2:
        new_str = new_str + test_str[i]

# Printing string after removal  
print ("The string after removal of i'th character : " + new_str)
```

**输出:**

```
The original string is : GeeksForGeeks
The string after removal of i'th character : GeksForGeeks

```

**注意:**这个解决方案比其他方法慢得多(具有 O(n^2 时间复杂度)。如果需要速度，方法#3 在逻辑上类似，速度更快(时间复杂度为 O(n))。

**Method 2 : Using `str.replace()`**

`replace()`可以用来执行移除任务，因为我们可以用空字符替换特定的索引，从而解决这个问题。

**缺点:**这种方法的主要缺点是，如果字符串中存在与 pos 处的字符匹配的重复项，则该方法会失败。i. `replace()`替换特定字符的所有出现，因此将替换位置 I 的所有字符的所有出现。如果替换字符在字符串中第一次出现，我们有时仍然可以使用该函数。

**代码#2 :** 演示使用`str.replace()`移除字符。

```
# Python code to demonstrate
# method to remove i'th character
# using replace()

# Initializing String 
test_str = "GeeksForGeeks"

# Printing original string 
print ("The original string is : " + test_str)

# Removing char at pos 3
# using replace
new_str = test_str.replace('e', '')

# Printing string after removal  
# removes all occurrences of 'e'
print ("The string after removal of i'th character( doesn't work) : " + new_str)

# Removing 1st occurrence of s, i.e 5th pos.
# if we wish to remove it.
new_str = test_str.replace('s', '', 1)

# Printing string after removal  
# removes first occurrences of s
print ("The string after removal of i'th character(works) : " + new_str)
```

**输出:**

```
The original string is : GeeksForGeeks
The string after removal of i'th character( doesn't work) : GksForGks
The string after removal of i'th character(works) : GeekForGeeks

```

**Method 3 : Using slice + concatenation**

一旦可以使用字符串切片并在位置 I 之前切片字符串，并在位置 I 之后切片。然后使用两者的字符串串联，第 I 个字符可以从字符串中删除。

**代码#3 :** 演示如何使用切片和串联来移除第 I 个字符。

```
# Python code to demonstrate
# method to remove i'th character
# using slice + concatenation

# Initializing String 
test_str = "GeeksForGeeks"

# Printing original string 
print ("The original string is : " + test_str)

# Removing char at pos 3
# using slice + concatenation
new_str = test_str[:2] +  test_str[3:]

# Printing string after removal  
# removes ele. at 3rd index
print ("The string after removal of i'th character : " + new_str)
```

**输出:**

```
The original string is : GeeksForGeeks
The string after removal of i'th character : GeksForGeeks

```

**Method 4 : Using `str.join()` and list comprehension**

在此方法中，字符串的每个元素首先被转换为列表的每个元素，然后它们中的每一个被连接以形成除指定索引之外的字符串。

**代码#4 :** 演示`str.join()`并列出移除第 I 个索引字符的理解。

```
# Python code to demonstrate
# method to remove i'th character
# using join() + list comprehension

# Initializing String 
test_str = "GeeksForGeeks"

# Printing original string 
print ("The original string is : " + test_str)

# Removing char at pos 3
# using join() + list comprehension
new_str = ''.join([test_str[i] for i in range(len(test_str)) if i != 2])

# Printing string after removal  
# removes ele. at 3rd index
print ("The string after removal of i'th character : " + new_str)
```

**输出:**

```
The original string is : GeeksForGeeks
The string after removal of i'th character : GeksForGeeks

```