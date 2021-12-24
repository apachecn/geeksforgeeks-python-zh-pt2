# Python 字符串下()方法

> 原文:[https://www.geeksforgeeks.org/python-string-lower/](https://www.geeksforgeeks.org/python-string-lower/)

Python String **lower()** 方法将字符串中的所有大写字符转换为小写字符并返回。

> **语法:**
> 
> string.lower()
> 
> **参数:**
> 
> lower()方法不接受任何参数。
> 
> **返回:**
> 
> 返回给定字符串的小写字符串

### 示例 1 **:** 仅包含字母字符的字符串

## 蟒蛇 3

```py
# Python3 program to show the
# working of lower() function
text = 'GeEks FOR geeKS'

print("Original String:")
print(text)

# lower() function to convert
# string to lower_case
print("\nConverted String:")
print(text.lower())
```

**输出:**

```py
Original String:
GeEks FOR geeKS

Converted string:
geeks for geeks
```

### 示例 **2:** 带字母数字字符的字符串

## 蟒蛇 3

```py
# Python3 program to show the
# working of lower() function
text = 'G3Ek5 F0R gE3K5'

print("Original String:")
print(text)

# lower() function to convert
# string to lower_case
print("\nConverted String:")
print(text.lower())
```

**输出:**

```py
Original String:
G3Ek5 F0R gE3K5

Converted String:
g3ek5 f0r ge3k5
```

### **例 3**

lower()方法的一个常见应用是检查两个字符串是否相同。

## 蟒蛇 3

```py
# Python3 program to show the
# working of lower() function
text1 = 'GEEKS For GEEKS'

text2 = 'gEeKS fOR GeeKs'

# Comparison of strings using
# lower() method
if(text1.lower() == text2.lower()):
    print("Strings are same")
else:
    print("Strings are not same")
```

**输出:**

```py
Strings are same
```