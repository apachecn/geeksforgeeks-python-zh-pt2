# Python 程序替换字符串中的每第 n 个字符

> 原文:[https://www . geesforgeks . org/python-每第 n 个字符串替换程序/](https://www.geeksforgeeks.org/python-program-to-replace-every-nth-character-in-string/)

给定一个字符串，任务是编写一个 Python 程序，用给定值 k 替换字符串中的每第 n 个字符。

**示例:**

> **输入:** test_str =“极客 forgeeks 最适合所有极客”，K = ' { content } ' 2019；，N = 5
> 
> **输出:**极客$ orge $ ks i $ bes $ for $ all $ eeks
> 
> **说明:**每 5 个字符转换成$。
> 
> **输入** : test_str =“极客 forgeeks 最适合所有极客”，K = '* '，N = 5
> 
> **输出**:极客*乔治*我*贝斯*所有* eeks
> 
> **说明:**每出现 5 次转换为*。

**方法 1 :** 使用[循环](https://www.geeksforgeeks.org/loops-in-python/)和[枚举()](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，我们执行每个字符的迭代，并通过执行取模来检查它的第 n 次出现，即通过 n 求余数。如果它的第 n 次出现，该字符被 k 替换。

**例**

## 蟒蛇 3

```py
# initializing string
test_str = "geeksforgeeks is best for all geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = '{content}apos;

# initializing N
N = 5

res = ''
for idx, ele in enumerate(test_str):

    # add K if idx is multiple of N
    if idx % N == 0 and idx != 0:
        res = res + K
    else:
        res = res + ele

# printing result
print("String after replacement : " + str(res))
```

**输出:**

> 最初的字符串是:极客 forgeeks 最适合所有极客
> 
> 替换后的字符串:极客$ orge $ ks i $ bes $ for $ all $ eeks

**方法 2 :** 使用[生成器表达式](https://www.geeksforgeeks.org/generator-expressions/)、[连接()](https://www.geeksforgeeks.org/join-function-python/)和[枚举()](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，字符串的构造使用 join()进行。枚举()有助于获取所需的索引。生成器表达式为这个问题提供了一种简化方法。

**例**

## 蟒蛇 3

```py
# initializing string
test_str = "geeksforgeeks is best for all geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = '{content}apos;

# initializing N
N = 5

res = ''.join(ele if idx % N or idx == 0 else K for idx,
              ele in enumerate(test_str))

# printing result
print("String after replacement : " + str(res))
```

**输出:**

> 最初的字符串是:极客 forgeeks 最适合所有极客
> 
> 替换后的字符串:极客$ orge $ ks i $ bes $ for $ all $ eeks