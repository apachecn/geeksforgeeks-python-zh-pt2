# 用 Python 中的 replace()替换一个子串

> 原文:[https://www . geesforgeks . org/replace-in-python-to-replace-a-substring/](https://www.geeksforgeeks.org/replace-in-python-to-replace-a-substring/)

给定可能包含一个或多个“AB”的字符串。将字符串中出现的所有“AB”替换为“C”。

示例:

```
Input  : str = "helloABworld"
Output : str = "helloCworld"

Input  : str = "fghABsdfABysu"
Output : str = "fghCsdfCysu"

```

该问题已有解决方案，请参考[在不使用额外空间](https://www.geeksforgeeks.org/replace-occurrences-string-ab-c-without-using-extra-space/)链接的情况下，用 C 替换字符串 AB 的所有出现。我们在 python 中使用字符串数据类型的**替换()**方法快速解决了这个问题。

【replace()函数是如何工作的？
**str.replace(pattern，replaceWith，maxCount)** 取最少两个参数，用指定的子字符串 **replaceWith** 替换所有出现的**模式**。第三个参数**最大计数**是可选的，如果我们没有通过这个参数，那么替换函数将对所有模式的出现进行替换，否则它将只替换**最大计数**次模式的出现。

```
# Function to replace all occurrences of AB with C

def replaceABwithC(input, pattern, replaceWith):
    return input.replace(pattern, replaceWith)

# Driver program
if __name__ == "__main__":
    input   = 'helloABworld'
    pattern = 'AB'
    replaceWith = 'C'
    print (replaceABwithC(input,pattern,replaceWith))
```

输出:

```
'helloCworld'

```