# Python 程序将字符串转换为 K 大小的数字行

> 原文:[https://www . geesforgeks . org/python-program-to-convert-string-to-k-size-numeric-rows/](https://www.geeksforgeeks.org/python-program-to-convert-string-to-k-sized-numerical-rows/)

给定一串字母，将其转换为 K 大小的数字行，其中包含的数字是字符的位置值。

> **输入** : test_str = 'geeksforgeek '，K = 4
> **输出** : [[6，4，4，10]，[18，5，14，17]，[6，4，4，10]]
> **解释** : g 位于字母表中的第 6 位，因此 g→ 6，字符串在每第 4 个字符后被拆分
> 
> **输入** : test_str = 'geeksforgeek '，K = 3
> **输出** : [[6，4，4]，[10，18，5]，[14，17，6]，[4，4，10]]
> **解释** : g 位于字母表中的第 6 位，因此 g→ 6，字符串在第三个字符
> 后被拆分

**方法 1:使用 loop +** [**指数()**](https://www.geeksforgeeks.org/python-list-index/#:~:text=index()%20is%20an%20inbuilt,index%20where%20the%20element%20appears.&text=Parameters%20%3A,lowest%20index%20will%20be%20returned.)

在这种情况下，我们使用循环执行每个字符的迭代，并使用有序字符列表上的 index()获取字符在字母表中的所需位置。

## 蟒蛇 3

```
# initializing string
test_str = 'geeksforgeekscse'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = 4

alphabs = "abcdefghijklmnopqrstuvwxyz"

res = []
temp = []
for ele in test_str:

    # finding numerical position using index()
    temp.append(alphabs.index(ele))

    # regroup on K
    if len(temp) == K:
        res.append(temp)
        temp = []

# appending remaining characters
if temp != []:
    res.append(temp)

# printing result
print("Grouped and Converted String : " + str(res))
```

**输出:**

> 原始字符串为:geeksforgeeckscse
> 分组转换字符串:[[6，4，4，10]，[18，5，14，17]，[6，4，4，10]，[18，2，18，4]]

**方法二:使用 ljust()+order()+列表理解**

在这种情况下，我们使用 [ljust()](https://www.geeksforgeeks.org/python-string-ljust-rjust-center/) 执行要求填充具有相等长度行的任务，然后使用[order()](https://www.geeksforgeeks.org/ord-function-python/)、[列表理解](https://www.geeksforgeeks.org/comprehensions-in-python/)获得数字字母位置，使用切片有助于将列表转换为 K 分块矩阵。

## 蟒蛇 3

```
from math import ceil

# initializing string
test_str = 'geeksforgeekscse'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = 4

# filling the rear to K size rows
temp = test_str.ljust(ceil(len(test_str) / K) * K)

# convert to numerical characters
temp = [0 if char == ' ' else (ord(char) - 97) for char in temp]

# slice and render to matrix
res = [temp[idx: idx + K] for idx in range(0, len(temp), K)]

# printing result
print("Grouped and Converted String : " + str(res))
```

**输出:**

> 原始字符串为:geeksforgeeckscse
> 分组转换字符串:[[6，4，4，10]，[18，5，14，17]，[6，4，4，10]，[18，2，18，4]]