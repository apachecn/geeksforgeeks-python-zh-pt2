# Python 字符串中心()方法

> 原文:[https://www.geeksforgeeks.org/python-string-center-method/](https://www.geeksforgeeks.org/python-string-center-method/)

Python String **center()** 方法创建并返回一个用指定字符填充的新字符串。

> **语法:**
> 
> string.center(长度[，fillchar])
> 
> **参数:**
> 
> *   **长度:**用字符填充后的字符串长度。
> *   **fillchar:** (可选)需要填充的字符。如果没有提供，空间将作为默认参数。
> 
> **返回:**
> 
> 返回用指定 fillchar 填充的字符串，并且不修改原始字符串。

### 示例 1:带有默认填充字符的 center()方法

## 计算机编程语言

```
# Python program to illustrate
# string center() in python
string = "geeks for geeks"

new_string = string.center(24)

# here filchar not provided so takes space by default.
print "After padding String is: ", new_string
```

**输出:**

```
After padding String is:      geeks for geeks
```

### **示例 2:** 带# fillchar 的中心()方法

## 计算机编程语言

```
# Python program to illustrate
# string center() in python
string = "geeks for geeks"

new_string = string.center(24, '#')

# here fillchar is provided
print "After padding String is:", new_string
```

**输出:**

```
After padding String is: ####geeks for geeks#####
```