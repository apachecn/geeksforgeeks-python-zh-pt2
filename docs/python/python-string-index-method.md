# Python 字符串索引()方法

> 原文:[https://www.geeksforgeeks.org/python-string-index-method/](https://www.geeksforgeeks.org/python-string-index-method/)

在字符串中查找字符串(子字符串)是一个在日常生活中有许多用途的应用程序。Python 使用函数 index()来提供这一功能，该函数返回字符串中第一个出现的子字符串的位置。

> **语法:**
> 
> ch .索引(ch1、begp、end)
> 
> **参数:**
> 
> *   **ch1 :** 要搜索的字符串。
> *   **begp(默认:0) :** 该功能指定搜索开始的位置。
> *   **endp(默认值:string_len) :** 该函数指定搜索必须结束的位置。
> 
> **返回值:**
> 
> 返回找到的子字符串的第一个位置。
> 
> 例外:
> 
> 如果找不到参数字符串，则引发值错误。

### 例 1

## 计算机编程语言

```py
# Python code to demonstrate the working of 
# index()

# initializing target string 
ch = "geeksforgeeks"

# initializing argument string 
ch1 = "geeks"

# using index() to find position of "geeks"
# starting from 2nd index 
# prints 8
pos = ch.index(ch1,2)

print ("The first position of geeks after 2nd index : ",end="")
print (pos)
```

**输出:**

```py
The first position of geeks after 2nd index : 8
```

> **注:**index()方法类似于 [find()](https://www.geeksforgeeks.org/python-string-find/) 。唯一的区别是，如果没有找到搜索到的字符串，find()将返回-1，在这种情况下，index()将引发异常。

### 示例 2:异常

**值错误:**在目标字符串中找不到参数字符串的情况下，会出现此错误。

## 计算机编程语言

```py
# Python code to demonstrate the exception of 
# index()

# initializing target string 
ch = "geeksforgeeks"

# initializing argument string 
ch1 = "gfg"

# using index() to find position of "gfg"
# raises error
pos = ch.index(ch1)

print ("The first position of gfg is : ",end="")
print (pos)
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/aa5904420c1c3aa072ede56ead7e26ab.py", line 12, in 
    pos = ch.index(ch1)
ValueError: substring not found
```

### **例 3**

**实际应用:**该功能用于提取目标词前后的**后缀或前缀长度。下面的例子显示了来自交流电压指令的总位长，给定字符串中的信息。**

## 计算机编程语言

```py
# Python code to demonstrate the application of 
# index()

# initializing target strings
voltages = ["001101 AC", "0011100 DC", "0011100 AC", "001 DC"] 

# initializing argument string 
type = "AC"

# initializing bit-length calculator
sum_bits = 0

for i in voltages : 

    ch = i

    if (ch[len(ch)-2]!='D'):
       # extracts the length of bits in string 
       bit_len = ch.index(type)-1

       # adds to total
       sum_bits = sum_bits + bit_len

print ("The total bit length of AC is : ",end="")
print (sum_bits)
```

**输出:**

```py
The total bit length of AC is : 13
```