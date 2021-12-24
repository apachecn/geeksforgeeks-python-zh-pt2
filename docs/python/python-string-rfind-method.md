# Python 字符串 rfind()方法

> 原文:[https://www.geeksforgeeks.org/python-string-rfind-method/](https://www.geeksforgeeks.org/python-string-rfind-method/)

python String***rfind()***方法返回给定字符串中找到的子字符串的最高索引。如果没有找到，则返回-1。

> **语法:**
> 
> str.rfind(sub，start，end)
> 
> **参数:**
> 
> *   **sub:** 是给定字符串中需要搜索的子串。
> *   **开始:**需要在管柱内检查接头的开始位置。
> *   **结束:**字符串中需要检查后缀的结束位置。
> 
> **注意:**如果没有提供开始和结束索引，那么默认情况下，它将 0 和 length-1 作为开始和结束索引，其中结束索引不包括在我们的搜索中。
> 
> **返回:**
> 
> 如果在给定字符串中找到子字符串，则返回该子字符串的最高索引；如果没有找到，则返回-1。
> 
> 例外:
> 
> 值错误:当在目标字符串中找不到参数字符串时，会引发此错误。

### 例 1

## 蟒蛇 3

```py
# Python program to demonstrate working of rfind()
# in whole string
word = 'geeks for geeks'

# Returns highest index of the substring
result = word.rfind('geeks')
print ("Substring 'geeks' found at index :", result )

result = word.rfind('for')
print ("Substring 'for' found at index :", result )

word = 'CatBatSatMatGate'

# Returns highest index of the substring
result = word.rfind('ate')
print("Substring 'ate' found at index :", result)
```

**输出:**

```py
Substring 'geeks' found at index : 10
Substring 'for' found at index : 6
Substring 'ate' found at index : 13
```

### 例 2

## 蟒蛇 3

```py
# Python program to demonstrate working of rfind()
# in a sub-string
word = 'geeks for geeks'

# Substring is searched in 'eeks for geeks'
print(word.rfind('ge', 2))

# Substring is searched in 'eeks for geeks' 
print(word.rfind('geeks', 2))

# Substring is searched in 'eeks for geeks' 
print(word.rfind('geeks ', 2))

# Substring is searched in 's for g'
print(word.rfind('for ', 4, 11))
```

**输出:**

```py
10
10
-1
6
```

### 例 3: **实际应用**

在字符串检查中很有用。检查给定的子字符串是否存在于某个字符串中。

## 蟒蛇 3

```py
# Python program to demonstrate working of rfind()
# to search a string
word = 'CatBatSatMatGate'

if (word.rfind('Ate') != -1):
    print ("Contains given substring ")
else:
    print ("Doesn't contains given substring")
```

**输出:**

```py
Doesn't contains given substring
```