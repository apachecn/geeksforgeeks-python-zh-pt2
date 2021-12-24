# Python 字符串|数字

> 原文:[https://www.geeksforgeeks.org/python-string-digits/](https://www.geeksforgeeks.org/python-string-digits/)

在 Python3 中， **`string.digits`** 是一个预初始化的字符串，用作字符串常量。在 Python 中，`string.digits`会给出小写字母‘0123456789’。

> **语法:**字符串。数字
> 
> **参数:**不取任何参数，因为它不是函数。
> 
> **返回:**返回所有数字字母。

**注意:**一定要导入字符串库函数才能使用`string.digits`

**代码#1 :**

```py
# import string library function 
import string 

# Storing the value in variable result 
result = string.digits 

# Printing the value 
print(result) 
```

**输出:**

```py
0123456789
```

**代码#2 :** 给定代码检查输入的字符串是否只有数字字母

```py
# importing string library function 
import string 

# Function checks if input string 
# har only digits or not 
def check(value): 
    for letter in value: 

        # If anything other than digit 
        # letter is present, then return 
        # False, else return True 
        if letter not in string.digits: 
            return False
    return True

# Driver Code 
input1 = "0123 456 789"
print(input1, "--> ",  check(input1)) 

input2 = "12.0124"
print(input2, "--> ", check(input2)) 

input3 = "12345"
print(input3, "--> ", check(input3)) 
```

**输出:**

```py
0123 456 789 -->  False
12.0124 -->  False
12345 -->  True
```

**应用:**
字符串常量**数字**可以在很多实际应用中使用。让我们看一个代码，解释如何使用数字生成给定大小的强随机密码。

```py
# Importing random to generate 
# random string sequence 
import random 

# Importing string library function 
import string 

def rand_pass(size): 

    # Takes random choices from 
    # ascii_letters and digits 
    generate_pass = ''.join([random.choice( string.ascii_uppercase + 
                                            string.ascii_lowercase + 
                                            string.digits) 
                                            for n in range(size)]) 

    return generate_pass 

# Driver Code  
password = rand_pass(10) 
print(password) 

```

**输出:**

```py
2R8gaoDKqn
```