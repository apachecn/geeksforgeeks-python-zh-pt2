# Python 字符串计数()方法

> 原文:[https://www.geeksforgeeks.org/python-string-count-method/](https://www.geeksforgeeks.org/python-string-count-method/)

Python String **count()** 函数是 Python 编程语言中的一个内置函数，它返回给定字符串中子串的出现次数。

> **语法:**
> 
> string.count(子字符串，start=…，end=…)
> 
> **参数:**
> 
> *   count()函数有一个强制参数和两个可选参数。
>     *   **强制参数:**
>         *   substring–要查找其计数的字符串。
>     *   **可选参数:**
>         *   *开始(可选)*–搜索开始的字符串中的起始索引。
>         *   *结束(可选)*–在搜索结束的字符串中结束索引。
> 
> **返回值:**
> 
> count()方法返回一个整数，表示子串在给定字符串中出现的**次次数**。

### 示例 1:无可选参数的 count()方法**的实现**

## 蟒蛇 3

```py
# Python program to demonstrate the use of
# count() method without optional parameters 

# string in which occurrence will be checked
string = "geeks for geeks" 

# counts the number of times substring occurs in 
# the given string and returns an integer
print(string.count("geeks"))
```

**输出:**

```py
2
```

### 示例 2:使用可选参数实现 count()方法

## **蟒蛇 3**

```py
# Python program to demonstrate the use of
# count() method  using optional parameters

# string in which occurrence will be checked
string = "geeks for geeks" 

# counts the number of times substring occurs in 
# the given string between index 0 and 5 and returns 
# an integer
print(string.count("geeks", 0, 5))

print(string.count("geeks", 0, 15))
```

****输出:****

```py
1
2
```