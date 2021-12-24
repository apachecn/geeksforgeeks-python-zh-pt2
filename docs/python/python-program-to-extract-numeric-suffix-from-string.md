# Python 程序从字符串中提取数字后缀

> 原文:[https://www . geesforgeks . org/python-从字符串中提取程序-数字-后缀/](https://www.geeksforgeeks.org/python-program-to-extract-numeric-suffix-from-string/)

给定一串嵌入了数字的字符。任务是编写一个 Python 程序来提取所有尾随的数字，即字符串的后缀。

**示例:**

> **输入:** test_str = "GFG04 "
> 
> **输出:** 04
> 
> **说明:** 04 是由此提取的字符串和数字的后缀。
> 
> **输入:**test _ str =“gfg 143”
> 
> **输出:** 143
> 
> **说明:** 143 是由此提取的字符串和数字的后缀。

**方法#1:使用 loop+**[**is digit()**](https://www.geeksforgeeks.org/python-string-isdigit-application/)**+**[**切片**](https://www.geeksforgeeks.org/python-list-slicing/)

在这种情况下，使用切片对字符串进行反转，并使用 isdigit 记录第一个非数字元素的出现，最后，对列表进行切片，直到元素再次反转，以获得后缀编号。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Suffix numbers
# Using loop + isdigit() + slicing 

# initializing string
test_str = "GFG04"

# printing original string
print("The original string is : " + str(test_str))

# loop for fetching the 1st non digit index 
rev_str = test_str[::-1] 
temp_idx = 0

for idx, ele in enumerate(rev_str):
    if not ele.isdigit():
        temp_idx = idx
        break

# reversing the extracted string to
# get number 
res = rev_str[:temp_idx][::-1]

# printing result
print("Suffix number : " + str(res))
```

**Output**

```
The original string is : GFG04
Suffix number : 04
```

**方法 2:使用** [**regex**](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

可以使用适当的正则表达式来解决这个问题。为这个问题提供了一个简洁的解决方案。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Suffix numbers
# Using regex
import re

# initializing string
test_str = "GFG04"

# printing original string
print("The original string is : " + str(test_str))

# regex to extract number 
res = re.search(r"(\d+){content}quot;, test_str).group()

# printing result
print("Suffix number : " + str(res))
```

**Output**

```
The original string is : GFG04
Suffix number : 04
```