# Python–反转一行中的一个单词，保持特殊字符不变

> 原文:[https://www . geeksforgeeks . org/python-反向一行一个单词并保持特殊字符不变/](https://www.geeksforgeeks.org/python-reverse-a-words-in-a-line-and-keep-the-special-characters-untouched/)

反转一行中包括数字在内的所有单词中的字符，但在同一位置保留特殊字符和符号不变。考虑下面的例子。

> **输入:**‘班加罗尔是@#$！123 再次锁定 2020 年 7 月'应改为
> **输出:** 'erolagnaB si@#$！321 dekcol niaga ni 0202luj '
> 
> **输入:**‘班加罗尔是@#$！123 2020 年 7 月再次锁定锁定'应改为
> **输出:**' erolagnb si @ # $！dek col 321 dek col niaga ni 0202 luj '

看上面的例子，每个单词都是颠倒的，如果有什么特殊字符，那么围绕这个特殊字符的单词就会颠倒过来。

## 蟒蛇 3

```
def reverStringsInLine(s):

    sl = s.split(' ')
    rsl = ''

    for word in sl:
        str_word = ''
        rev_sub_word = ''

        for ch in word:

            if ch.isalnum():
                str_word += ch

            else:

                # If it is special character, then
                # reverse non special characters and
                # append special character

                rev_sub_word += str_word[::-1] + ch

                # Clear the old stached character, as
                # it is already reversed
                str_word = ''

        # Keep appening each words, also add words
        # ending with non-special character
        r_word = rev_sub_word + str_word[::-1]
        rsl += r_word + ' '
    return rsl

s = 'Bangalore is@#$!123locked locked again in jul2020'

print(reverStringsInLine(s))
```

**输出:**

```
erolagnaB si@#$!dekcol321 dekcol niaga ni 0202luj 
```