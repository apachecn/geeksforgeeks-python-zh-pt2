# Python 字符串| ascii _ 小写

> 原文:[https://www . geesforgeks . org/python-string-ascii _ 小写/](https://www.geeksforgeeks.org/python-string-ascii_lowercase/)

在 Python3 中， **`ascii_lowercase`** 是一个预初始化的字符串，用作字符串常量。在 Python 中，字符串`ascii_lowercase` 将给出小写字母‘abcdefghijklmnopqrstuvwxyz’。

> **语法:**string . ascii _ 小写
> 
> **参数:**不取任何参数，因为它不是函数。
> 
> **返回:**返回所有小写字母。

**注意:**确保导入字符串库函数以便使用 ascii _ 小写。

**代码#1 :**

```py
# import string library function 
import string 

# Storing the value in variable result 
result = string.ascii_lowercase

# Printing the value 
print(result) 
```

**输出:**

```py
abcdefghijklmnopqrstuvwxyz
```

**代码#2 :** 给定代码检查输入的字符串是否只有较低的 ASCII 字符。

```py
# importing string library function 
import string 

# Function checks if input string 
# has lower only ascii letters or not 
def check(value): 
    for letter in value: 

        # If anything other than lower ascii 
        # letter is present, then return 
        # False, else return True 
        if letter not in string.ascii_lowercase: 
            return False
    return True

# Driver Code 
input1 = "GeeksForGeeks"
print(input1, "--> ",  check(input1)) 

input2 = "geeks for geeks"
print(input2, "--> ", check(input2)) 

input3 = "geeksforgeeks"
print(input3, "--> ", check(input3)) 
```

**输出:**

```py
GeeksForGeeks -->  False
geeks for geeks -->  False
geeksforgeeks -->  True
```

**应用:**
弦常数`ascii_lowercase` 可以在很多实际应用中使用。我们来看一个代码，解释如何使用`ascii_lowercase` 生成给定大小的强随机密码。

```py
# Importing random to generate 
# random string sequence 
import random 

# Importing string library function 
import string 

def rand_pass(size): 

    # Takes random choices from 
    # ascii_letters and digits 
    generate_pass = ''.join([random.choice( 
                        string.ascii_lowercase + string.digits) 
                        for n in range(size)]) 

    return generate_pass 

# Driver Code  
password = rand_pass(10) 
print(password) 

```

**输出:**

```py
52v3bdyk63
```