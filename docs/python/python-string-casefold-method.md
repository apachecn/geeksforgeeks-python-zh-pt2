# Python 字符串 casefold()方法

> 原文:[https://www . geesforgeks . org/python-string-casefold-method/](https://www.geeksforgeeks.org/python-string-casefold-method/)

Python 字符串 **casefold()** 方法用于实现无 case 字符串匹配。它类似于 [lower()](https://www.geeksforgeeks.org/python-string-lower/) 字符串方法，但是 case **移除了字符串中存在的所有 case 区别**。即在比较时忽略案例。

> **语法:**
> 
> string.casefold()
> 
> **参数:**
> 
> casefold()方法不接受任何参数。
> 
> **返回值:**
> 
> 它返回大小写折叠的字符串，该字符串被转换为小写。

### **例 1:小写转换字符串**

## 蟒蛇 3

```
# Python program to convert string in lower case
string = "GEEKSFORGEEKS"

# print lowercase string
print("lowercase string: ",string.casefold())
```

**输出:**

```
lowercase string: geeksforgeeks
```

### **例 2:检查字符串是否为回文**

## 蟒蛇 3

```
# Program to check if a string
#  is palindrome or not

# change this value for a different output
str = 'geeksforgeeks'

# make it suitable for caseless comparison
str = str.casefold()

# reverse the string
rev_str = reversed(str)

# check if the string is equal to its reverse
if str == rev_str:
      print("palindrome")
else:
      print("not palindrome")
```

**输出:**

```
not palindrome
```

### **例 3:统计一个字符串中的元音**

## 蟒蛇 3

```
# Program to count 
# the number of each 
# vowel in a string

# string of vowels
v = 'aeiou'

# change this value for a different result
str = 'Hello, have you try geeksforgeeks?'

# input from the user
# str = input("Enter a string: ")

# caseless comparisions
str = str.casefold()

# make a dictionary with 
# each vowel a key and value 0
c = {}.fromkeys(v,0)

# count the vowels
for char in str:
          if char in c:
                  c[char] += 1
print(c)
```

**输出:**

```
{'a': 1, 'e': 6, 'i': 0, 'o': 3, 'u': 1}
```