# Python–大写半字符串

> 原文:[https://www.geeksforgeeks.org/python-uppercase-half-string/](https://www.geeksforgeeks.org/python-uppercase-half-string/)

给定一个字符串，执行字符串后面部分的大写。

> **输入**:test _ str = ' geesforgek '
> **输出**:geesforgek
> **解释**:字符串后半部分上移。
> 
> **输入**:test _ str = ' apple '
> **输出**:apple
> **解释**:弦后半部分上翘。

**方法#1:使用 upper() + loop + len()**

在这种情况下，我们计算半个索引，然后仅对位于字符串另一半的字符执行 upper()。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Uppercase Half String
# Using upper() + loop + len()

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# computing half index
hlf_idx = len(test_str) // 2

res = ''
for idx in range(len(test_str)):

    # uppercasing later half
    if idx >= hlf_idx:
      res += test_str[idx].upper()
    else :
      res += test_str[idx]

# printing result 
print("The resultant string : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The resultant string : geeksfORGEEKS

```

**方法 2:使用列表理解+连接()+上()**

这类似于上面的方法，只是任务是使用列表理解以速记方式执行的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Uppercase Half String
# Using list comprehension + join() + upper()

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# computing half index
hlf_idx = len(test_str) // 2

# join() used to create result string 
res = ''.join([test_str[idx].upper() if idx >= hlf_idx else test_str[idx]
         for idx in range(len(test_str)) ])

# printing result 
print("The resultant string : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The resultant string : geeksfORGEEKS

```