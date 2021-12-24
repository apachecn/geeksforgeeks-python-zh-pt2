# Python 字符串解码()方法

> 原文:[https://www.geeksforgeeks.org/python-strings-decode-method/](https://www.geeksforgeeks.org/python-strings-decode-method/)

decode()是 Python 2 中 Strings 中指定的方法。
此方法用于从一种编码方案转换到所需的编码方案，在该编码方案中，参数字符串被编码。这与编码相反。它接受编码字符串的编码进行解码，并返回原始字符串。

> 语法:**解码(编码，错误)**
> 
> **参数:**
> **编码:**指定解码必须基于的编码。
> **错误:**决定发生错误时如何处理，例如“严格”在出现异常时引发 Unicode 错误，“忽略”忽略发生的错误。
> 
> **返回:**从编码字符串中返回原始字符串。

**代码#1 :** 代码解码字符串

```py
# Python code to demonstrate 
# decode() 

# initializing string  
str = "geeksforgeeks"

# encoding string  
str_enc = str.encode(encodeing='utf8') 

# printing the encoded string 
print ("The encoded string in base64 format is : ",) 
print (str_enc )

# printing the original decoded string  
print ("The decoded string is : ",) 
print (str_enc.decode('utf8', 'strict'))
```

**输出:**

```py
The encoded string in base64 format is :  Z2Vla3Nmb3JnZWVrcw==

The decoded string is :  geeksforgeeks

```

**应用:**
编码和解码一起可以用于在后端存储密码的简单应用，以及许多其他应用，如处理信息保密的密码学。
下面描述了密码应用的一个小演示。

**代码#2 :** 代码演示编解码的应用

```py
# Python code to demonstrate 
# application of encode-decode 

# input from user 
# user = input() 
# pass = input() 

user = "geeksforgeeks"
passw = "i_lv_coding"

# converting password to base64 encoding 
passw = passw.encode('base64', 'strict') 

# input from user 
# user_login = input() 
# pass_login = input() 

user_login = "geeksforgeeks"

# wrongly entered password 
pass_wrong = "geeksforgeeks"

print ("Password entered : " + pass_wrong )

if(pass_wrong == passw.decode('base64', 'strict')): 
    print ("You are logged in !!")
else : print ("Wrong Password !!")

print( '\r')

# correctly entered password 
pass_right = "i_lv_coding"

print ("Password entered : " + pass_right )

if(pass_right == passw.decode('base64', 'strict')): 
    print ("You are logged in !!")
else : 
    print ("Wrong Password !!")
```

**输出:**

```py
Password entered : geeksforgeeks
Wrong Password!!

Password entered : i_lv_coding
You are logged in!!

```