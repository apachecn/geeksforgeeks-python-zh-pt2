# Python 中的 string . oct digits

> 原文:[https://www.geeksforgeeks.org/string-octdigits-in-python/](https://www.geeksforgeeks.org/string-octdigits-in-python/)

在 Python3 中， **`string.octdigits`** 是一个预初始化的字符串，用作字符串常量。在 Python 中，`string.octdigits`会给出十八进制字母‘01234567’。

> **语法:** string.octdigits
> 
> **参数:**不取任何参数，因为它不是函数。
> 
> **返回:**返回所有十八位数字字母。

**注意:**一定要导入字符串库函数才能使用`string.octdigits`

**代码#1 :**

```py
# import string library function 
import string 

# Storing the value in variable result 
result = string.octdigits 

# Printing the value 
print(result) 
```

**输出:**

```py
01234567
```

**代码#2 :** 给定代码检查输入的字符串是否只有十八位数字字母

```py
# importing string library function 
import string 

# Function checks if input string 
# has only octdigits or not 
def check(value): 
    for letter in value: 

        # If anything other than octdigit 
        # letter is present, then return 
        # False, else return True 
        if letter not in string.octdigits: 
            return False
    return True

# Driver Code 
input1 = "01234567"
print(input1, "--> ",  check(input1)) 

input2 = "abcdefABCDEF"
print(input2, "--> ", check(input2)) 

input3 = "abcdefghGEEK"
print(input3, "--> ", check(input3)) 

input4 = "0123"
print(input3, "--> ", check(input4)) 

input5 = "567"
print(input3, "--> ", check(input5)) 
```

**输出:**

```py
01234567 -->  True
abcdefABCDEF -->  False
abcdefghGEEK -->  False
abcdefghGEEK -->  True
abcdefghGEEK -->  True

```

**应用:**

弦常数**八位数**可以在很多实际应用中使用。让我们看一个代码，解释如何使用数字生成给定大小的强随机密码。

```py
# Importing random to generate 
# random string sequence 
import random 

# Importing string library function 
import string 

def rand_pass(size): 

    # Takes random choices from 
    # string.octdigits 
    generate_pass = ''.join([random.choice(string.octdigits) 
                        for n in range(size)]) 

    return generate_pass 

# Driver Code  
password = rand_pass(10) 
print(password)   
```

**输出:**

```py
5077306643

```