# Python 程序打印 k 个字符然后跳过一个字符串中的 k 个字符

> 原文:[https://www . geesforgeks . org/python-程序-打印-k 字符-然后-跳过-k 字符-字符串/](https://www.geeksforgeeks.org/python-program-to-print-k-characters-then-skip-k-characters-in-a-string/)

给定一个字符串，交替提取 K 个字符。

> **输入**:test _ str = ' geeksgeeksisbestforgeks '，K = 4
> **输出**:geekskisforg
> **解释**:每隔 4 个交替范围进行切片。
> **输入**:test _ str = ' geeksgeeksisbest '，K = 4
> **输出**:geeksis
> **解释**:每隔 4 个交替范围进行切片。

**方法#1:使用循环+切片**

在这种情况下，我们使用切片来执行获取 K 个字符的任务，使用循环来执行连接任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Alternate K Length characters
# Using loop + slicing 

# initializing string
test_str = 'geeksgeeksisbestforgeeks' 

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 4

res = ''

# skipping k * 2 for altering effect
for idx in range(0, len(test_str), K * 2):

    # concatenating K chars
    res += test_str[idx : idx + K]

# printing result 
print("Transformed String : " + str(res)) 
```

**输出:**

```py
The original string is : geeksgeeksisbestforgeeks
Transformed String : geekksisforg

```

**方法 2:使用列表理解+连接()**

这类似于上面的方法，唯一的区别是它的一个线性方法，join()用于执行转换回字符串的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Alternate K Length characters
# Using list comprehension + join()

# initializing string
test_str = 'geeksgeeksisbestforgeeks' 

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 4

# slicing K using slicing, join for converting back to string
res = ''.join([test_str[idx : idx + K] for idx in range(0, len(test_str), K * 2)])

# printing result 
print("Transformed String : " + str(res)) 
```

**输出:**

```py
The original string is : geeksgeeksisbestforgeeks
Transformed String : geekksisforg

```