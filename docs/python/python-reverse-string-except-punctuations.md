# Python–除标点符号外的反串

> 原文:[https://www . geesforgeks . org/python-反向-字符串-除-标点符号/](https://www.geeksforgeeks.org/python-reverse-string-except-punctuations/)

给定一个带标点符号的字符串，执行字符串反转，在它们的位置留下标点符号。

> **输入**:test _ str = ' geeks @ # for&% % gee)ks '
> **输出**:skeg @ # ROF&% % ske)eg
> % T6】解释:整串颠倒，除了标点符号。
> 
> **输入**:test _ str = ' geeks @ # for&% % gee)ks '[仅子串反转]
> **输出**:skeg @ # ROF&% % EEG)sk
> **解释**:仅子串反转。

**方法一:使用循环+栈+标点+拆分()**

在这种情况下，我们使用堆栈来执行字符串反转，检查标点符号，如果当前字符是一个，我们追加它。split 方法用于处理空格的情况，在反转时需要忽略空格。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reverse String except punctuations
# Using loop + stack + punctuation + split()
from string import punctuation

# initializing string
test_str = 'geeks# for&%% gee)ks'

# printing original string
print("The original string is : " + str(test_str))

# getting punctuations
punc_set = set(punctuation)
res = []
for sub in test_str.split(' '):

    # getting all alphabets
    alphas = [chr for chr in sub if chr not in punc_set]
    for chr in sub:

        # checking for punctuations
        if chr not in punc_set:
            res.append(alphas.pop())
            continue
        else:
            res.append(chr)

    # handling spaces
    res.append(' ')
res = "".join(res)

# printing result
print("The Reversed String ignoring punctuation : " + str(res))
```

**Output**

```py
The original string is : geeks#for&%%gee)ks
The Reversed String ignoring punctuation : skeeg#rof&%%ske)eg 
```

**方法 2:使用 groupby() + isalnum() [用于子串特定反转]**

在这种情况下，我们在标点符号之间形成每个子串的分组，并在它们之间反转它们，而不是整体。isalnum()用于检查所有字母。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reverse String except punctuations
# Using groupby() + isalnum() [ for substring specific reversal ]
from itertools import groupby

# initializing string
test_str = 'geeks# for&%% gee)ks'

# printing original string
print("The original string is : " + str(test_str))

res = ''

# grouping all sections
for ele, sub in groupby(test_str, str.isalnum):
    sub = list(sub)

    # reversal on alphanumeric occurrence
    if ele:
        sub = sub[::-1]

    # joining all subparts
    res += ''.join(sub)

# printing result
print("The Reversed String ignoring punctuation [substring] : " + str(res))
```

**Output**

```py
The original string is : geeks#for&%%gee)ks
The Reversed String ignoring punctuation [substring] : skeeg#rof&%%eeg)sk
```