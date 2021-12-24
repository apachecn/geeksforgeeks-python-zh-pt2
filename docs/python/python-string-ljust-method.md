# Python 字符串 ljust()方法

> 原文:[https://www.geeksforgeeks.org/python-string-ljust-method/](https://www.geeksforgeeks.org/python-string-ljust-method/)

Python String ljust()方法根据指定的宽度左对齐字符串，如果未传递“fillchr”参数，则用空格填充行的剩余空间。

> **语法:**
> 
> 光源(len，fillchr)
> 
> **参数:**
> 
> *   len:用于扩展字符串的宽度。
> *   fillchr(可选):要填充剩余空间的字符。
> 
> **返回值:**
> 
> 在原始字符串右侧替换给定字符后，返回给定长度的新字符串。

### 例 1

## 蟒蛇 3

```
# example string
string = 'gfg'
width = 5

# print left justified string
print(string.ljust(width))
```

**输出:**

```
gfg  
```

**说明:**

这里，定义的最小宽度是 5。因此，结果字符串的最小长度为 5。并且，字符串“gfg”向左对齐，这样就在单词的右边留下了两个空格。

### 例 2

## 蟒蛇 3

```
# Python3 code to demonstrate
# the working of ljust()

lstr = "I love geeksforgeeks"

# Printing the original string
print ("The original string is : \n", lstr, "\n")

# Printing the left aligned
# string with "-" padding
print ("The left aligned string is : ")
print (lstr.ljust(40, '-'))
```

**输出:**

```
The original string is : 
 I love geeksforgeeks 

The left aligned string is : 
I love geeksforgeeks--------------------
```