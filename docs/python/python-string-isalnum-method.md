# Python 字符串 isalnum()方法

> 原文:[https://www.geeksforgeeks.org/python-string-isalnum-method/](https://www.geeksforgeeks.org/python-string-isalnum-method/)

Python 字符串 **isalnum()** 方法检查给定字符串中的所有字符是否都是字母数字。**字母数字**是指字母或数字。

> **语法:**
> 
> string_name.isalnum（）
> 
> **参数:**
> 
> isalnum()方法不接受任何参数
> 
> **返回:**
> 
> *   **真:**如果所有字符都是字母数字
> *   **假:**如果一个或多个字符不是字母数字

### 示例 isalnum()的工作原理

## 计算机编程语言

```py
# Python program to demonstrate the use of
# isalnum() method  

# here a,b and c are characters and 1,2 and 3
# are numbers
string = "abc123"
print(string.isalnum())

# here a,b and c are characters and 1,2 and 3 
# are numbers but space is not a alphanumeric 
# character
string = "abc 123" 
print(string.isalnum())
```

**输出:**

```py
True
False
```