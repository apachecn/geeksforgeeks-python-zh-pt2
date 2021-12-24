# Python 字符串|六位数

> 原文:[https://www.geeksforgeeks.org/python-string-hexdigits/](https://www.geeksforgeeks.org/python-string-hexdigits/)

在 Python3 中， **`string.hexdigits`** 是一个预初始化的字符串，用作字符串常量。在 Python 中，`string.hexdigits`将给出十六进制字母‘0123456789 abcdefbcdef’。

> **语法:**字符串。十六位数字
> 
> **参数:**不取任何参数，因为它不是函数。
> 
> **返回:**返回所有十六进制数字字母。

**注意:**确保导入字符串库函数以便使用 string.hexdigits

**代码#1 :**

```py
# import string library function 
import string 

# Storing the value in variable result 
result = string.hexdigits 

# Printing the value 
print(result) 
```

**输出:**

```py
0123456789abcdefABCDEF
```

**代码#2 :** 给定代码检查字符串输入是否只有十六进制数字字母

```py
# importing string library function 
import string 

# Function checks if input string 
# has only hexdigits or not 
def check(value): 
    for letter in value: 

        # If anything other than hexdigit 
        # letter is present, then return 
        # False, else return True 
        if letter not in string.hexdigits: 
            return False
    return True

# Driver Code 
input1 = "0123456789abcdef"
print(input1, "--> ",  check(input1)) 

input2 = "abcdefABCDEF"
print(input2, "--> ", check(input2)) 

input3 = "abcdefghGEEK"
print(input3, "--> ", check(input3)) 
```

**输出:**

```py
0123456789abcdef -->  True
abcdefABCDEF -->  True
abcdefghGEEK -->  False
```

**应用:**
字符串常量**六位数**可以在很多实际应用中使用。让我们看一个代码，解释如何使用数字生成给定大小的强随机密码。

```py
# Importing random to generate 
# random string sequence 
import random 

# Importing string library function 
import string 

def rand_pass(size): 

    # Takes random choices from 
    # string.hexdigits 
    generate_pass = ''.join([random.choice(string.hexdigits) 
                        for n in range(size)]) 

    return generate_pass 

# Driver Code  
password = rand_pass(10) 
print(password)  
```

**输出:**

```py
e497FEe2bC
```