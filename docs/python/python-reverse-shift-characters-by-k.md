# Python–按 K 反转字符

> 原文:[https://www . geesforgeks . org/python-reverse-shift-characters-by-k/](https://www.geeksforgeeks.org/python-reverse-shift-characters-by-k/)

给定一个字符串，将每个字符根据其字母位置反向移位 K，包括循环移位。

> **输入** : test_str = 'bccd '，K = 1
> **输出** : abbc
> **解释**:b 前面的 1 个字母是' a '以此类推。
> **输入** : test_str = 'bccd '，K = 2
> **输出** : zaab
> **解释**:b 前 2 个字母为' z '(四舍五入)以此类推。

**方法:使用 maketrans() + upper() +列表理解+ translate() +切片**

在这种情况下，我们使用 maketrans()和切片将每个字符转换为其 K 移位版本。upper()用于处理所有大写字符，translate()用于根据 maketrans()创建的查找翻译表执行翻译。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reverse Shift characters by K
# using maketrans() + upper() + list comprehension + translate() + slicing

# initializing string
test_str = 'GeeksForGeeks'

# printing original String
print("The original string is : " + str(test_str))

# initializing K
K = 10

alpha_chars = 'abcdefghijklmnopqrstuvwxyz'

# converted to uppercase
alpha_chars2 = alpha_chars.upper()

# maketrans used for lowercase translation
lower_trans = str.maketrans(alpha_chars, alpha_chars[ -K:] + alpha_chars[ : -K])

# maketrans used for uppercase translation
upper_trans = str.maketrans(alpha_chars2, alpha_chars2[ -K:] + alpha_chars2[ : -K])

# merge lookups
lower_trans.update(upper_trans)

# make translation from lookups
res = test_str.translate(lower_trans)

# printing result
print("The converted String : " + str(res))
```

**Output**

```py
The original string is : GeeksForGeeks
The converted String : WuuaiVehWuuai
```