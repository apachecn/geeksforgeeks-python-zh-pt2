# Python 程序在字符串中增加后缀数

> 原文:[https://www . geesforgeks . org/python-程序到增量-后缀-字符串中的数字/](https://www.geeksforgeeks.org/python-program-to-increment-suffix-number-in-string/)

给定一个字符串，任务是编写一个 Python 程序来增加字符串末尾的数字。

> **输入** : test_str = 'geeks006'
> **输出** : geeks7
> **解释**:后缀 006 递增至 7。
> 
> **输入** : test_str = 'geeks007'
> **输出** : geeks8
> **解释**:后缀 007 递增至 8。

**方法#1:使用 findall()+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)**+**[**替换()**](https://www.geeksforgeeks.org/python-string-replace/)

在这个策略中，我们使用 findall()执行查找数字的任务，然后执行分离数字字符串和前缀字符串的任务，然后执行数字字符串的增量。最后，字符串被连接，得到一个前缀，后跟一个递增的数字。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Increment Suffix Number
# Using findall() + join() + replace()
import re

# initializing string
test_str = 'geeks006'

# printing original string
print("The original string is : " + str(test_str))

# getting suffix number 
reg = re.compile(r'[ 0 - 9]')
mtch = reg.findall(test_str)

# getting number 
num = ''.join(mtch[-3 : ])
pre_str = test_str.replace(num, '')

# Increment number 
add_val = int(num) + 1

# joining prefix str and added value 
res = pre_str + str(add_val)

# printing result 
print("Incremented numeric String : " + str(res)) 
```

**输出:**

```
The original string is : geeks006
Incremented numeric String : geeks61
```

**方法 2:使用 sub() + group() + zfill()**

在本例中，我们使用 group()和 incrementing 执行数字分组任务，zfill()用于填充数字中所需的前导值。sub()用于查找字符串的数字部分。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Increment Suffix Number
# Using sub() + group() + zfill()
import re

# initializing string
test_str = 'geeks006'

# printing original string
print("The original string is : " + str(test_str))

# fstring used to form string 
# zfill fills values post increment
res = re.sub(r'[0-9]+{content}apos;,
             lambda x: f"{str(int(x.group())+1).zfill(len(x.group()))}", 
             test_str)

# printing result 
print("Incremented numeric String : " + str(res)) 
```

**输出:**

```
The original string is : geeks006
Incremented numeric String : geeks007
```