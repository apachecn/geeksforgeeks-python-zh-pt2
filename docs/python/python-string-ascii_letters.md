# Python 中的 ascii _ 字母

> 原文:[https://www.geeksforgeeks.org/python-string-ascii_letters/](https://www.geeksforgeeks.org/python-string-ascii_letters/)

在 Python3 中， ***ascii_letters*** 是用作字符串常量的预初始化字符串。
***ascii _ 字母*** 基本上是***ascii _ 小写*** 和***ascii _ 大写*** 字符串常量的串联。此外，生成的值不依赖于区域设置，因此不会改变。

**语法:**

```
string.ascii_letters
```

**注意:**确保导入字符串库函数以便使用 *ascii_letters* 。

**参数:**

```
 Doesn't take any parameter, since it's not a function. 
```

**返回:**

```
 Return all ASCII letters (both lower and upper case)
```

**代码#1 :**

```
# import string library function
import string

# Storing the value in variable result
result = string.ascii_letters

# Printing the value
print(result)
```

**输出:**

```
abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
```

**代码#2 :**
给定的代码检查输入的字符串是否只有 ASCII 字符。

```
# importing string library function
import string

# Function checks if input string
# has only ascii letters or not
def check(value):
    for letter in value:

        # If anything other than ascii
        # letter is present, then return
        # False, else return True
        if letter not in string.ascii_letters:
            return False
    return True

# Driver Code
input1 = "GeeksForGeeks"
print(input1, "--> ",  check(input1))

input2 = "Geeks for Geeks"
print(input2, "--> ", check(input2))

input3 = "Geeks_for_geeks"
print(input3, "--> ", check(input3))
```

**输出:**

```
GeeksForGeeks -->  True
Geeks for Geeks -->  False
Geeks_for_geeks -->  False
```

**应用:**
字符串常量 ascii_letters 可以在很多实际应用中使用。
我们来看一个代码，解释如何使用 ascii_letters 生成给定大小的强随机密码。

**代码#1 :**

```
# Importing random to generate
# random string sequence
import random

# Importing string library function
import string

def rand_pass(size):

    # Takes random choices from
    # ascii_letters and digits
    generate_pass = ''.join([random.choice(
                        string.ascii_letters + string.digits)
                        for n in range(size)])

    return generate_pass

# Driver Code 
password = rand_pass(10)
print(password)

```

**输出:**

```
oQjI5MOXQ3
```

**注意:**以上给出的代码每次都会打印随机(不同)的密码，以提供的大小为准。

**代码#2 :**
说如果要生成随机密码，但是要从给定的字符串集合中。让我们看看如何使用 ascii 字母来实现这一点:

```
# Importing random to generate
# random string sequence
import random

# Importing string library function
import string

def rand_pass(size, scope = string.ascii_letters + string.digits):

    # Takes random choices from ascii_letters and digits
    generate_pass = ''.join([random.choice(scope)
                             for n in range(size)])

    return generate_pass

# Driver Code 
password = rand_pass(10, 'Geeks3F0rgeeKs')
print(password)
```

**输出:**

```
kg3g03keG3
```