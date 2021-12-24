# Python 集|检查给定的字符串是否为异程序

> 原文:[https://www . geesforgeks . org/python-set-check-when-given-string-heterogram-not/](https://www.geeksforgeeks.org/python-set-check-whether-given-string-heterogram-not/)

给定一串小写字符。任务是检查给定的字符串是否是杂凑图。异形词是指字母表中没有一个字母出现超过一次的单词、短语或句子。

示例:

```
Input : S = "the big dwarf only jumps"
Output : Yes
Each alphabet in the string S is occurred
only once.

Input : S = "geeksforgeeks" 
Output : No
Since alphabet 'g', 'e', 'k', 's' occurred
more than once.

```

对于这个问题我们已经有了解决方案，请参考[检查给定的字符串是否是异码](https://www.geeksforgeeks.org/check-whether-given-string-heterogram-not/)链接。我们可以使用[设置数据结构](https://www.geeksforgeeks.org/sets-in-python/)在 python 中快速解决这个问题。方法很简单，

1.  In order to check whether a sentence is a heteromorphous word, we only care about letters, not any other characters, so we separate the list of all letters in the sentence.
2.  Convert the list of letters into a set, because the set contains unique values. If the length of the set is equal to the number of letters, which means that each letter appears once, the sentence is a heteronym, otherwise it is not.

```
# Function to Check whether a given string is Heterogram or not 

def heterogram(input):

     # separate out list of alphabets using list comprehension
     # ord function returns ascii value of character
     alphabets = [ ch for ch in input if ( ord(ch) >= ord('a') and ord(ch) <= ord('z') )]

     # convert list of alphabets into set and 
     # compare lengths
     if len(set(alphabets))==len(alphabets):
         print ('Yes')
     else:
         print ('No')

# Driver program
if __name__ == "__main__":
    input = 'the big dwarf only jumps'
    heterogram(input)
```

输出:

```
Yes

```