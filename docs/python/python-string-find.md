# Python String find()方法

> 原文:[https://www.geeksforgeeks.org/python-string-find/](https://www.geeksforgeeks.org/python-string-find/)

Python String find()方法返回在给定字符串中找到的子字符串的最低索引。如果没有找到，则返回-1。

> **语法:**
> 
> str.find(sub，start，end)
> 
> **参数:**
> 
> *   **sub:** 是给定字符串中需要搜索的子串。
> *   **开始:**需要在管柱内检查接头的开始位置。
> *   **结束:**字符串中需要检查后缀的结束位置。
> 
> **注#1:** 如果没有提供开始和结束索引，那么默认情况下，它采用 0 和 length-1 作为开始和结束索引，其中结束索引不包括在我们的搜索中。
> 
> **返回:**
> 
> 如果在给定字符串中找到子字符串，则返回该子字符串的最低索引。如果没有找到，则返回-1。
> 
> **注 2:**find()方法类似于[索引()](https://www.geeksforgeeks.org/python-string-index-applications/)。唯一的区别是，如果没有找到搜索到的字符串，find()将返回-1，在这种情况下，index()将引发异常。

### 示例 1:查找()没有开始和结束参数

## 蟒蛇 3

```py
word = 'geeks for geeks'

# returns first occurrence of Substring
result = word.find('geeks')
print ("Substring 'geeks' found at index:", result )

result = word.find('for')
print ("Substring 'for ' found at index:", result )

# How to use find()
if (word.find('pawan') != -1):
    print ("Contains given substring ")
else:
    print ("Doesn't contains given substring")
```

**输出:**

```py
Substring 'geeks' found at index: 0
Substring 'for ' found at index: 6
Doesn't contains given substring
```

### 示例 2:使用开始和结束参数查找()

## 蟒蛇 3

```py
word = 'geeks for geeks'

# Substring is searched in 'eks for geeks' 
print(word.find('ge', 2)) 

# Substring is searched in 'eks for geeks' 
print(word.find('geeks ', 2)) 

# Substring is searched in 's for g' 
print(word.find('g', 4, 10)) 

# Substring is searched in 's for g' 
print(word.find('for ', 4, 11))
```

**输出:**

```py
10
-1
-1
6
```