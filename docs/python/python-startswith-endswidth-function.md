# Python | startswith()和 endswith()函数

> 原文:[https://www . geesforgeks . org/python-start swith-end swidth-function/](https://www.geeksforgeeks.org/python-startswith-endswidth-function/)

Python 库提供了许多内置方法，其中一个是用于字符串相关操作的 **startswith()** 和 **endswith()** 函数。

**开头为()**

**语法**

```
str.startswith(search_string, start, end)
```

**参数:**

> **search_string :** 要搜索的字符串。
> **开始:**开始搜索字符串的索引。
> **end:***str***的** end 索引，考虑搜索。

**使用:**

*   **startswith()** 函数用于检查给定的句子是否以某个特定的字符串开头。
*   开始和结束参数是可选的。
*   当我们只想考虑搜索原始字符串的某个特定子字符串时，我们可以使用它们。

**返回:**
返回值为二进制。如果原句以搜索字符串 else 开头，则函数返回 ***【真】*** 【假】 。

**end with()**

**语法:**

```
str.endswith( search_string, start, end)
```

**参数:**

> **search_string :** 要搜索的字符串。
> **开始:**开始搜索字符串的索引。
> **End:***str***的** End 索引，考虑搜索。

**使用:**

*   **endswith()** 函数用于检查给定的句子是否以某个特定的字符串结尾。
*   开始和结束参数是可选的。
*   当我们只想考虑搜索原始字符串的某个特定子字符串时，我们可以使用它们。

**返回:**
返回值为二进制。如果原始句子以搜索字符串 else 结束，则函数返回 ***【真】*** 【假】 。

下面是解释 ***开始于()*** 和 ***结束于()*** 的代码:

```
# Python code to implement startswith()
# and endswith() function.

str = "GeeksforGeeks"

# startswith()
print(str.startswith("Geeks"))
print(str.startswith("Geeks", 4, 10))
print(str.startswith("Geeks", 8, 14))

print("\n")

# endswith
print(str.endswith("Geeks"))
print(str.endswith("Geeks", 2, 8))
print(str.endswith("for", 5, 8))
```

输出:

```
True
False
True

True
False
True
```