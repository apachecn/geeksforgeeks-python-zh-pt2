# Python–从字符串中删除索引范围

> 原文:[https://www . geesforgeks . org/python-remove-index-ranges-from-string/](https://www.geeksforgeeks.org/python-remove-index-ranges-from-string/)

给定一个字符串和范围列表，删除范围中出现的所有字符。

> **输入** : test_str = 'geeksforgeeks 最适合极客'，range_list = [(3，6)，(7，10)]
> **输出**:极客最适合极客
> **解释**:所需范围移除。
> 
> **输入** : test_str = 'geeksforgeeks 最适合极客'，range_list = [(3，6)]
> **输出**:geogeeks 最适合极客
> **解释**:所需范围移除。

**方法#1:使用循环**

在这种情况下，我们检查每个范围，重制字符串，考虑到索引不在于使用条件语句的范围检查。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove index ranges from String 
# Using loop

# initializing strings
test_str1 = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string 1 is : " + str(test_str1))

# initializing ranges list 
range_list = [(3, 6), (7, 10), (14, 17)]

res = ""

for idx, chr in enumerate(test_str1):
  for strt_idx, end_idx in range_list:

    # checking for ranges and appending 
    if strt_idx <= idx + 1 <= end_idx: 
      break
  else:
    res += chr

# printing result 
print("The reconstructed string : " + str(res)) 
```

**Output**

```
The original string 1 is : geeksforgeeks is best for geeks
The reconstructed string : geeksbest for geeks

```

**方法 2:使用 any() +列表理解+ join()**

在本文中，我们使用 any()执行检查字符串索引的任务，并使用列表理解来相应地重构字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove index ranges from String 
# Using any() + list comprehension + join()

# initializing strings
test_str1 = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string 1 is : " + str(test_str1))

# initializing ranges list 
range_list = [(3, 6), (7, 10), (14, 17)]

# using any() to check for strings in index ranges
res = ''.join(chr for idx, chr in enumerate(test_str1, 1) if not any(strt_idx <= idx <= end_idx 
         for strt_idx, end_idx in range_list))

# printing result 
print("The reconstructed string : " + str(res)) 
```

**Output**

```
The original string 1 is : geeksforgeeks is best for geeks
The reconstructed string : geeksbest for geeks

```