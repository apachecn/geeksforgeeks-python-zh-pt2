# Python 程序将字符串中每个单词的第一个和最后一个字符大写

> 原文:[https://www . geesforgeks . org/python-program-将字符串中每个单词的第一个和最后一个字符大写/](https://www.geeksforgeeks.org/python-program-to-capitalize-the-first-and-last-character-of-each-word-in-a-string/)

给定字符串，任务是大写字符串中每个单词的第一个和最后一个字符。

**例:**

```
Input: hello world 
Output: HellO WorlD

Input: welcome to geeksforgeeks
Output: WelcomE TO GeeksforgeekS

```

**方法:**

*   Use the index to access the last element.
*   Capitalize the first word using the `title()` method.
*   Then use the `join()` method to connect each word.
*   Perform all operations inside lambda, and write code one line at a time.

下面是实现。

```
# Python program to capitalize
# first and last character of 
# each word of a String

# Function to do the same
def word_both_cap(str):

    #lamda function for capitalizing the
    # first and last letter of words in 
    # the string
    return ' '.join(map(lambda s: s[:-1]+s[-1].upper(), 
                        s.title().split()))

# Driver's code
s = "welcome to geeksforgeeks"
print("String before:", s)
print("String after:", word_both_cap(str))
```

**输出:**

```
String before: welcome to geeksforgeeks
String after: WelcomE TO GeeksforgeekS

```