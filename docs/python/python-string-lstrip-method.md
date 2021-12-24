# Python String lstrip()方法

> 原文:[https://www.geeksforgeeks.org/python-string-lstrip-method/](https://www.geeksforgeeks.org/python-string-lstrip-method/)

Python String **lstrip()** 方法返回去掉前导字符的字符串副本(基于传递的字符串参数)。如果没有传递参数，它将删除前导空格。

> **语法:**
> 
> string.lstrip(字符)
> 
> **参数:**
> 
> *   **字符**【可选】:作为前导字符删除的一组字符。
> 
> **返回:**
> 
> 返回一个去掉前导字符的字符串副本。

### 例 1

## 蟒蛇 3

```
# Python3 program to demonstrate the use of  
# lstrip() method using default parameter

# string which is to be stripped 
string = "   geeksforgeeks"

# Removes spaces from left. 
print(string.lstrip())
```

**输出:**

```
geeksforgeeks
```

### 例 2

## 蟒蛇 3

```
# Python3 program to demonstrate the use of  
# lstrip() method using optional parameters

# string which is to be stripped 
string = "++++x...y!!z* geeksforgeeks"

# Removes given set of characters from left. 
print(string.lstrip("+.!*xyz"))
```

**输出:**

```
geeksforgeeks
```

### **例 3**

## 蟒蛇 3

```
# string which is to be stripped 
string = "geeks for geeks"

# Argument doesn't contain leading 'g' 
# So, no characters are removed 
print(string.lstrip('ge'))
```

**输出:**

```
ks for geeks
```

### 示例 **4**

当我们试图剥离除字符串以外的任何内容时，会出现运行时错误。

## 蟒蛇 3

```
# Python3 program to demonstrate the use of 
# strip() method error 

string = " geeks for geeks "
list =[1, 2, 3] 

# prints the error message 
print(list.lstrip())
```

**输出:**

```
print(list.lstrip()) 
AttributeError: 'list' object has no attribute 'lstrip'
```