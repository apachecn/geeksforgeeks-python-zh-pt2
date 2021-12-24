# Python |删除给定句子中所有重复的单词

> 原文:[https://www . geesforgeks . org/python-remove-duplicates-word-given-句子/](https://www.geeksforgeeks.org/python-remove-duplicates-words-given-sentence/)

给定一个包含 n 个单词/字符串的句子。删除所有彼此相似的重复单词/字符串。
示例:

```
Input : Geeks for Geeks
Output : Geeks for

Input : Python is great and Java is also great
Output : is also Java Python and great
```

我们可以使用 [python Counter()方法](https://www.geeksforgeeks.org/counters-in-python-set-1/)快速解决这个问题。方法很简单。
1)将空格分隔的输入句子拆分成单词。
2)因此，为了首先将所有这些字符串连接在一起，我们将在给定的字符串列表中连接每个字符串。
3)现在使用 Counter 方法创建一个字典，将字符串作为键，将它们的频率作为值。
4)连接每个单词都是唯一的，形成一个字符串。

## 计算机编程语言

```
from collections import Counter

def remov_duplicates(input):

    # split input string separated by space
    input = input.split(" ")

    # joins two adjacent elements in iterable way
    for i in range(0, len(input)):
        input[i] = "".join(input[i])

    # now create dictionary using counter method
    # which will have strings as key and their
    # frequencies as value
    UniqW = Counter(input)

    # joins two adjacent elements in iterable way
    s = " ".join(UniqW.keys())
    print (s)

# Driver program
if __name__ == "__main__":
    input = 'Python is great and Java is also great'
    remov_duplicates(input)
```

**Output**

```
and great Java Python is also

```

**替代方法:-**

## 计算机编程语言

```
# Program without using any external library
s = "Python is great and Java is also great"
l = s.split()
k = []
for i in l:

    # If condition is used to store unique string
    # in another list 'k'
    if (s.count(i)>=1 and (i not in k)):
        k.append(i)
print(' '.join(k))
```

**Output**

```
Python is great and Java also

```

**方法 3:** 另一个更短的实现:

## 蟒蛇 3

```
# Python3 program

string = 'Python is great and Java is also great'

print(' '.join(dict.fromkeys(string.split())))
```

**Output**

```
Python is great and Java also

```

https://youtu.be/tTjBhgJ

-在 T0 上