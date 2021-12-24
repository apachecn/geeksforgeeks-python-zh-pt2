# 寻找重叠子串索引的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-find-indexs-of-overlapping-substrings/](https://www.geeksforgeeks.org/python-program-to-find-indices-of-overlapping-substrings/)

为了计算 Python 中重叠子字符串的数量，我们可以使用 Re 模块。为了获得索引，我们将使用 re.finditer()方法。但是它只返回非重叠索引的计数。

**示例:**

> **输入:**字符串:“geeksforgeeksforgeeks 模式:【极客 forgeeks】
> **输出:**【0，8】
> **解释:**模式是将字符串从第 0 个索引重叠到第 12 个索引，再从第 8 个索引重叠到第 20 个索引。因此，输出是重叠的起始位置，即索引 0 和索引 8。
> 
> **输入:**字符串:“barfoobarfoobarfoobarfoobarfoo 图案:
> **输出:**【3，9，15，21】
> **说明:**图案与索引 3，9，15，21 的字符串重叠。

此方法仅从具有多次出现重叠模式的字符串中返回非重叠索引的计数。下面是描述使用 *finditer()* 方法的程序。

## 蟒蛇 3

```py
# Import required module
import re

# Function to depict use of finditer() method
def CntSubstr(pattern, string):

    # Array storing the indices
    a = [m.start() for m in re.finditer(pattern, string)]
    return a

# Driver Code
string = 'geeksforgeeksforgeeks'
pattern = 'geeksforgeeks'

# Printing index values of non-overlapping pattern
print(CntSubstr(pattern, string))
```

**输出:**

```py
[0]

```

因此，为了获得重叠的索引，我们需要做的是跳出模式中的正则表达式。显式函数中的定义有助于部分选择字符。

**进场:**

1.  *re.finditer()* 有助于找到匹配对象出现的索引。当它返回一个可迭代对象时， *start()* 方法有助于返回索引，否则它将显示在某个位置找到了一个匹配对象。
2.  使用 re 模块进行匹配的标准方法是贪婪的，这意味着匹配的字符数最多。因此，*呢？={0}* 有助于最小数量的匹配。
3.  为了匹配部分字符，re.escape()有助于转义之前添加的特殊字符，如*？={0}* 。
4.  结果是通过添加 som 修改， *finditer()* 方法返回一个重叠索引列表。

**以下是上述方法的实现:**

## 蟒蛇 3

```py
# Import required module
import re

# Explicit function to Count
# Indices of Overlapping Substrings
def CntSubstr(pattern, string):
    a = [m.start() for m in re.finditer(
        '(?={0})'.format(re.escape(pattern)), string)]
    return a

# Driver Code
string1 = 'geeksforgeeksforgeeks'
pattern1 = 'geeksforgeeks'

string2 = 'barfoobarfoobarfoobarfoobarfoo'
pattern2 = 'foobarfoo'

# Calling the function
print(CntSubstr(pattern1, string1))
print(CntSubstr(pattern2, string2))
```

**输出:**

```py
[0, 8]
[3, 9, 15, 21]

```