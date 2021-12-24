# Python 中的字符串.标点符号

> 原文:[https://www.geeksforgeeks.org/string-punctuation-in-python/](https://www.geeksforgeeks.org/string-punctuation-in-python/)

在 Python3 中， **`string.punctuation`** 是一个预初始化的字符串，用作字符串常量。在 Python 中，`string.punctuation`会给出所有的标点符号集。

> **语法:**字符串。标点符号
> 
> **参数:**不取任何参数，因为它不是函数。
> 
> **返回:**返回所有标点符号集。

**注意:**一定要导入字符串库函数才能使用`string.punctuation`

**代码#1 :**

```py
# import string library function 
import string 

# Storing the sets of punctuation in variable result 
result = string.punctuation 

# Printing the punctuation values 
print(result) 
```

**输出:**

```py
!"#$%&'()*+, -./:;<=>?@[\]^_`{|}~

```

**代码#2 :** 给出标点符号的代码测试。

```py
# import string library function 
import string 

# An input string.
Sentence = "Hey, Geeks !, How are you?"

for i in Sentence:

    # checking whether the char is punctuation.
    if i in string.punctuation:

        # Printing the punctuation values 
        print("Punctuation: " + i)

```

**输出:**

```py
Punctuation:,
Punctuation: !
Punctuation:,
Punctuation: ?

```