# Python–保留字符串的前 N 个元素，并将剩余元素替换为 K

> 原文:[https://www . geeksforgeeks . org/python-保留字符串的前 n 个元素并用 k 替换剩余元素/](https://www.geeksforgeeks.org/python-retain-first-n-elements-of-a-string-and-replace-the-remaining-by-k/)

给定一个字符串，保留前 N 个元素，用 k 替换其余元素

> **输入**:test _ str = ' geeks forgeks '，N = 5，K = "@"
> **输出**:geeks @ @ @ @ @ @ @
> **解释**:前 N 个元素保留，其余替换为 K。
> 
> **输入**:test _ str = ' geeks forgeks '，N = 5，K = " *
> **输出** : geeks********
> **解释**:前 N 个元素保留，其余替换为 K

**方法#1:使用*运算符+ len() +切片**

在这种情况下，使用切片来保留 N，然后通过从 N 中减去 [len()](https://www.geeksforgeeks.org/python-string-length-len/) 提取的总长度来提取剩余的长度，然后使用*运算符重复 K char。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Retain N and Replace remaining by K
# Using * operator + len() + slicing

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing length needed
N = 4

# initializing remains char
K = "@"

# using len() and * operator to solve problem
res = test_str[:N] + K * (len(test_str) - N)

# printing result
print("The resultant string : " + str(res))
```

**Output**

```
The original string is : geeksforgeeks
The resultant string : geek@@@@@@@@@

```

**方法 2:使用 ljust() +切片+ len()**

在这种情况下，分配剩余字符的任务是使用 [ljust](https://www.geeksforgeeks.org/python-string-ljust-rjust-center/) 完成的，而不是*运算符。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Retain N and Replace remaining by K
# Using ljust() + slicing + len()

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing length needed
N = 4

# initializing remains char
K = "@"

# ljust assigns K to remaining string
res = test_str[:N].ljust(len(test_str), K)

# printing result
print("The resultant string : " + str(res))
```

**Output**

```
The original string is : geeksforgeeks
The resultant string : geek@@@@@@@@@

```