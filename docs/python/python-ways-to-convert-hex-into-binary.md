# Python |将十六进制转换为二进制的方法

> 原文:[https://www . geesforgeks . org/python-将十六进制转换为二进制的方法/](https://www.geeksforgeeks.org/python-ways-to-convert-hex-into-binary/)

十六进制到二进制的转换是一个非常常见的编程问题。在本文中，我们将看到解决上述问题的几种方法。

**方法#1:使用料仓和 zfill**

```
# Python code to demonstrate 
# conversion of a hex string
# to the binary string

# Initialising hex string
ini_string = "1a"
scale = 16

# Printing initial string
print ("Initial string", ini_string)

# Code to convert hex to binary
res = bin(int(ini_string, scale)).zfill(8)

# Print the resultant string
print ("Resultant string", str(res))
```

**输出:**

> 初始字符串 1a
> 结果字符串 00b11010

**方法#2:使用天真方法**

```
# Python code to demonstrate 
# conversion of hex string
# to binary string

import math

# Initialising hex string
ini_string = "1a"

# Printing initial string
print ("Initial string", ini_string)

# Code to convert hex to binary
n = int(ini_string, 16) 
bStr = ''
while n > 0:
    bStr = str(n % 2) + bStr
    n = n >> 1    
res = bStr

# Print the resultant string
print ("Resultant string", str(res))
```

**输出:**

> 初始字符串 1a
> 结果字符串 11010

**方法三:使用。格式**

```
# Python code to demonstrate 
# conversion of hex string
# to binary string

import math

# Initialising hex string
ini_string = "1a"

# Printing initial string
print ("Initial string", ini_string)

# Code to convert hex to binary
res = "{0:08b}".format(int(ini_string, 16))

# Print the resultant string
print ("Resultant string", str(res))
```

**输出:**

> 初始字符串 1a
> 结果字符串 00011010