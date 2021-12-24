# Python–从给定字符串中去除前后标点符号

> 原文:[https://www . geesforgeks . org/python-strip-from-给定字符串前后标点符号/](https://www.geeksforgeeks.org/python-strip-front-and-rear-punctuations-from-given-string/)

给定一个字符串条前后标点符号。

> **输入** : test_str = '%$Gfg 为 b！！est(*^'
> **输出** : Gfg 为 b！！est
> **说明**:前后标点被剥离。
> 
> **输入** : test_str = '%Gfg 为 b！！est(*^'
> **输出** : Gfg 为 b！！est
> **说明**:前后标点被剥离。

**方法一:使用标点()+循环**

在这种情况下，我们使用标点符号()从后面和前面检查标点符号，一旦找到非 pnc 字符，就会记录索引并拆分字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Strip Punctuations from String 
# Using loop + punctuation
from string import punctuation

# initializing string
test_str = '%$Gfg is b !! est(*^&*'

# printing original string
print("The original string is : " + str(test_str))

# getting first non-pnc idx 
frst_np = [idx for idx in range(len(test_str)) if test_str[idx] not in punctuation][0]

# getting rear non-pnc idx
rear_np = [idx for idx in range(len(test_str) - 1, -1, -1) if test_str[idx] not in punctuation][0]

# spittd string 
res = test_str[frst_np : rear_np + 1]

# printing result 
print("The stripped string : " + str(res)) 
```

**Output**

```
The original string is : %$Gfg is b!!est(*^&*
The stripped string : Gfg is b!!est

```

**方法 2:使用 strip() + split() + join()**

在本例中，我们使用 split()执行拆分任务，以获取单个单词，strip()用于移除标点符号。最后 join()用于执行单词的连接。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Strip Punctuations from String 
# Using strip() + split() + join()
from string import punctuation

# initializing string
test_str = '%$Gfg is b !! est(*^&*'

# printing original string
print("The original string is : " + str(test_str))

# strip is used to remove rear punctuations
res = ' '.join([ele.strip(punctuation) for ele in test_str.split()])

# printing result 
print("The stripped string : " + str(res)) 
```

**Output**

```
The original string is : %$Gfg is b!!est(*^&*
The stripped string : Gfg is b!!est

```