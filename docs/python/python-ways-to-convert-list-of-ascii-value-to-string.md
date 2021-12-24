# Python |将 ASCII 值列表转换为字符串的方法

> 原文:[https://www . geesforgeks . org/python-将 ascii 值列表转换为字符串的方法/](https://www.geeksforgeeks.org/python-ways-to-convert-list-of-ascii-value-to-string/)

给定一个 ASCII 值列表，编写一个 Python 程序，将这些值转换成它们的字符并形成一个字符串。下面给出了几个解决问题的方法。

**方法#1:使用朴素方法**

```
# Python code to demonstrate 
# conversion of list of ascii values
# to string

# Initialising list
ini_list = [71, 101, 101, 107, 115, 102, 
           111, 114, 71, 101, 101, 107, 115] 

# Printing initial list
print ("Initial list", ini_list)

# Using Naive Method
res = ""
for val in ini_list:
    res = res + chr(val)

# Printing resultant string
print ("Resultant string", str(res))
```

**输出:**

> 初始列表[71，101，101，107，115，102，111，114，71，101，101，107，115]
> 结果字符串 GeeksforGeeks

**方法 2:使用 map()**

```
# Python code to demonstrate 
# conversion of list of ascii values
# to string

# Initialising list
ini_list = [71, 101, 101, 107, 115, 102,
            111, 114, 71, 101, 101, 107, 115] 

# Printing initial list
print ("Initial list", ini_list)

# Using map and join
res = ''.join(map(chr, ini_list))

# Print the resultant string
print ("Resultant string", str(res))
```

**输出:**

> 初始列表[71，101，101，107，115，102，111，114，71，101，101，107，115]
> 结果字符串 GeeksforGeeks

**方法 3:使用连接和列表理解**

```
# Python code to demonstrate 
# conversion of a list of ascii values
# to string

# Initialising list
ini_list = [71, 101, 101, 107, 115, 102,
            111, 114, 71, 101, 101, 107, 115] 

# Printing initial list
print ("Initial list", ini_list)

# Using list comprehension and join
res = ''.join(chr(val) for val in ini_list)

# Print the resultant string
print ("Resultant string", str(res))
```

**输出:**

> 初始列表[71，101，101，107，115，102，111，114，71，101，101，107，115]
> 结果字符串 GeeksforGeeks