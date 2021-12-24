# Python String rindex()方法

> 原文:[https://www.geeksforgeeks.org/python-string-rindex-method/](https://www.geeksforgeeks.org/python-string-rindex-method/)

Python String rindex()方法返回字符串内部子字符串的最高索引(如果找到子字符串的话)。否则，它会引发异常。

> **语法:**
> 
> str.rindex(sub，start，end)
> 
> **参数:**
> 
> *   sub:它是需要在给定字符串中搜索的子字符串。
> *   开始:需要在字符串中检查 sub 的开始位置。
> *   end:需要在字符串中检查后缀的结束位置。
> 
> **注意:**如果没有提供开始和结束索引，那么默认情况下，它采用 0 和 length-1 作为开始和结束索引，其中结束索引不包括在我们的搜索中。
> 
> **返回:**
> 
> 如果找到子字符串，则返回字符串中子字符串的最高索引。否则会引发异常。
> 
> **错误和异常:**
> 
> 值错误:当在目标字符串中找不到参数字符串时，会引发此错误。

### **例 1**

```
input: text = 'geeks for geeks'
       result = text.rindex('geeks')
output: 10

input: text = 'geeks for geeks'
       result = text.rindex('ge')
output: 10
```

## 蟒蛇 3

```
# Python code to demonstrate working of rindex()
text = 'geeks for geeks'

result = text.rindex('geeks')
print("Substring 'geeks':", result)
```

**输出:**

```
Substring 'geeks': 10
```

### 例 2

## 蟒蛇 3

```
# Python code to demonstrate error by rindex()
text = 'geeks for geeks'

result = text.rindex('pawan')
print("Substring 'pawan':", result)
```

**错误:**

```
Traceback (most recent call last):
  File "/home/dadc555d90806cae90a29998ea5d6266.py", line 6, in 
    result = text.rindex('pawan')
ValueError: substring not found
```

### 例 3

## 蟒蛇 3

```
# Python code to demonstrate working of rindex()
# with range provided
quote = 'geeks for geeks'

# Substring is searched in ' geeks for geeks'
print(quote.rindex('ge', 2))

# Substring is searched in 0 to 10 range
print(quote.rindex('geeks', 0, 10))
```

**输出:**

```
10
0
```