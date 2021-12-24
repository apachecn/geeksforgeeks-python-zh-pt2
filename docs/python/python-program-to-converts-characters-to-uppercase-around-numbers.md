# 将数字周围的字符转换为大写的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-converts-characters-to-大写数字/](https://www.geeksforgeeks.org/python-program-to-converts-characters-to-uppercase-around-numbers/)

给定一个字符串，下面的程序将任意数字周围的字母字符转换为大写。

> **输入**:test _ str = ' geeks 4 eeks 为 best 1 F6 或 ge8eks'
> **输出**:geeks 4 eeks 为 best 1 F6 或 ge8 eks
> **解释** : S 和 G 被 4 包围。
> **输入**:test _ str = ' geeks 4 geeks best 1 F6 或 ge8eks'
> **输出**:geeks 4 geeks best 1 F6 或 ge8 eks
> **解释** : S 和 G 的上半部分被 4 包围。

**方法 1 :** *使用* [*上位()*](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/)*[*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*是数字()*](https://www.geeksforgeeks.org/python-string-isdigit-application/)*

*在本例中，我们对每个字符进行迭代，检查它是否是数字，如果是，则使用 upper()将周围的字母(下一个和上一个)转换为大写。*

## *蟒蛇 3*

```py
*# initializing string
test_str = 'geeks4geeks is best1 for ge8eks'

# printing original string
print("The original string is : " + str(test_str))

res = ''
for idx in range(len(test_str) - 1):
    if test_str[idx + 1].isdigit() or test_str[idx - 1].isdigit():
        res += test_str[idx].upper()
    else:
        res += test_str[idx]
#Adding last index character
else:
    res += test_str[idx+1]

# printing result
print("Transformed String : " + str(res))*
```

***输出:***

> *原始字符串是:geeks4geeks 是 ge8eks 的最佳 1*
> 
> *转换字符串:geekS4Geeks 是 gE8Ek 的最佳选择*

***方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/comprehensions-in-python/)*

*这类似于上面的方法，唯一的区别是下面的方法在一行中处理相同的问题。*

## *蟒蛇 3*

```py
*# initializing string
test_str = 'geeks4geeks is best1 for ge8eks'

# printing original string
print("The original string is : " + str(test_str))

# list comprehension offering 1 liner solution
res = [test_str[idx].upper() if test_str[idx + 1].isdigit() or test_str[idx - 1].isdigit() else test_str[idx] for idx in range(len(test_str) - 1)]
res = res + list(test_str[-1])

# printing result
print("Transformed String : " + ''.join(res))*
```

***输出:***

> *原始字符串是:geeks4geeks 是 ge8eks 的最佳 1*
> 
> *转换字符串:geekS4Geeks 是 gE8Ek 的最佳选择*