# Python 字符串分割线()方法

> 原文:[https://www . geesforgeks . org/python-string-splitlines-method/](https://www.geeksforgeeks.org/python-string-splitlines-method/)

Python String ***分割线()*** 方法用于分割线边界处的线。该函数返回字符串中的行列表，包括换行符(可选)。

> **语法:**
> 
> string.splitlines([keepends])
> 
> **参数:**
> 
> **保持结束**(可选) **:** 设置为**真时**换行符包含在结果列表中。这个**可以是一个数字**，指定换行符的位置，也可以是任意的 **Unicode 字符**，比如“\n”、“\r”、“\r\n”等作为字符串的边界。
> 
> **返回值:**
> 
> 返回字符串中线条的*列表*，在线条边界处断开。

**分割线()在以下线边界上分割:**

<figure class="table">

| 

表现

 | 

描述

 |
| --- | --- |
| \n | 换行 |
| \r | 回车 |
| \r\n | 回车+换行 |
| \x1c | 文件分隔符 |
| \x1d | 分组分隔符 |
| \x1e | 记录分离器 |
| \x85 | 下一行(C1 控制代码) |
| \v 或\x0b | 行列表 |
| \f 或\x0c | 换页 |
| \u2028 | 行分隔符 |
| \u2029 | 段落分隔符 |

</figure>

### 例 1

## 蟒蛇 3

```py
# Python code to illustrate splitlines()
string = "Welcome everyone to\rthe world of Geeks\nGeeksforGeeks"

# No parameters has been passed
print (string.splitlines( ))

# A specified number is passed
print (string.splitlines(0))

# True has been passed 
print (string.splitlines(True))
```

**输出:**

```py
['Welcome everyone to', 'the world of Geeks', 'GeeksforGeeks']
['Welcome everyone to', 'the world of Geeks', 'GeeksforGeeks']
['Welcome everyone to\r', 'the world of Geeks\n', 'GeeksforGeeks']
```

### 例 2

## 蟒蛇 3

```py
# Python code to illustrate splitlines()
string = "Cat\nBat\nSat\nMat\nXat\nEat"

# No parameters has been passed
print (string.splitlines( ))

# splitlines() in one line
print('India\nJapan\nUSA\nUK\nCanada\n'.splitlines())
```

**输出:**

```py
['Cat', 'Bat', 'Sat', 'Mat', 'Xat', 'Eat']
['India', 'Japan', 'USA', 'UK', 'Canada']
```

### 例 3: **实际应用**

在这段代码中，我们将了解如何使用 splitlines()的概念来计算字符串中每个单词的长度。

## 蟒蛇 3

```py
# Python code to get length of each words
def Cal_len(string):

    # Using splitlines() divide into a list
    li = string.splitlines()
    print (li)

    # Calculate length of each word
    l = [len(element) for element in li]
    return l

# Driver Code    
string = "Welcome\rto\rGeeksforGeeks"
print(Cal_len(string))
```

**输出:**

```py
['Welcome', 'to', 'GeeksforGeeks']
[7, 2, 13]
```