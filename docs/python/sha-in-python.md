# Python 中的 SHA

> 原文:[https://www.geeksforgeeks.org/sha-in-python/](https://www.geeksforgeeks.org/sha-in-python/)

SHA(安全散列算法)是由语言定义的一组加密散列函数，用于各种应用，如密码安全等。Python 在“ **hashlib** ”库中支持它的一些变体。这些可以使用 hashlib 的“algorithms _ guaranteed”函数找到。

```
# Python 3 code to check 
# available algorithms

import hashlib

# prints all available algorithms
print ("The available algorithms are : ", end ="")
print (hashlib.algorithms_guaranteed)
```

输出:

```
The available algorithms are : {'sha256', 'sha384', 'sha224', 'sha512', 'sha1', 'md5'}

```

首先，让我们讨论一下本文中将要使用的函数。

**相关功能:**

*   **encode() :** 将字符串转换为哈希函数可以接受的字节。
*   **hexdigest() :** 返回十六进制格式的编码数据。

**SHA Hash**

不同的 SHA 散列函数解释如下。

*   **SHA256 :** 这个哈希函数属于哈希类 SHA-2，它的内部块大小是 32 位。
*   **SHA384 :** 这个哈希函数属于哈希类 SHA-2，它的内部块大小是 32 位。这是截断版本之一。
*   **SHA224 :** 这个哈希函数属于哈希类 SHA-2，它的内部块大小是 32 位。这是截断版本之一。
*   **SHA512 :** 这个哈希函数属于哈希类 SHA-2，它的内部块大小是 64 位。
*   **SHA1:**160 位哈希函数在工作时类似于 MD5 哈希，但由于其安全漏洞而停止使用。

下面的代码实现了这些散列函数。

```
# Python 3 code to demonstrate
# SHA hash algorithms.

import hashlib

# initializing string
str = "GeeksforGeeks"

# encoding GeeksforGeeks using encode()
# then sending to SHA256()
result = hashlib.sha256(str.encode())

# printing the equivalent hexadecimal value.
print("The hexadecimal equivalent of SHA256 is : ")
print(result.hexdigest())

print ("\r")

# initializing string
str = "GeeksforGeeks"

# encoding GeeksforGeeks using encode()
# then sending to SHA384()
result = hashlib.sha384(str.encode())

# printing the equivalent hexadecimal value.
print("The hexadecimal equivalent of SHA384 is : ")
print(result.hexdigest())

print ("\r")

# initializing string
str = "GeeksforGeeks"

# encoding GeeksforGeeks using encode()
# then sending to SHA224()
result = hashlib.sha224(str.encode())

# printing the equivalent hexadecimal value.
print("The hexadecimal equivalent of SHA224 is : ")
print(result.hexdigest())

print ("\r")

# initializing string
str = "GeeksforGeeks"

# encoding GeeksforGeeks using encode()
# then sending to SHA512()
result = hashlib.sha512(str.encode())

# printing the equivalent hexadecimal value.
print("The hexadecimal equivalent of SHA512 is : ")
print(result.hexdigest())

print ("\r")

# initializing string
str = "GeeksforGeeks"

# encoding GeeksforGeeks using encode()
# then sending to SHA1()
result = hashlib.sha1(str.encode())

# printing the equivalent hexadecimal value.
print("The hexadecimal equivalent of SHA1 is : ")
print(result.hexdigest())
```

输出:

```
The hexadecimal equivalent of SHA256 is : 
f6071725e7ddeb434fb6b32b8ec4a2b14dd7db0d785347b2fb48f9975126178f

The hexadecimal equivalent of SHA384 is : 
d1e67b8819b009ec7929933b6fc1928dd64b5df31bcde6381b9d3f90488d253240490460c0a5a1a873da8236c12ef9b3

The hexadecimal equivalent of SHA224 is : 
173994f309f727ca939bb185086cd7b36e66141c9e52ba0bdcfd145d

The hexadecimal equivalent of SHA512 is : 
0d8fb9370a5bf7b892be4865cdf8b658a82209624e33ed71cae353b0df254a75db63d1baa35ad99f26f1b399c31f3c666a7fc67ecef3bdcdb7d60e8ada90b722

The hexadecimal equivalent of SHA1 is : 
4175a37afd561152fb60c305d4fa6026b7e79856

```

**说明:**上面的代码取 string，使用 encode()将其转换为等效字节，以便哈希函数可以接受。SHA 哈希函数对其进行编码，然后使用 hexdigest()，打印十六进制等效编码字符串。