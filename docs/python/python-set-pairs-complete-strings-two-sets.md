# Python 集|两组成对完整字符串

> 原文:[https://www . geesforgeks . org/python-set-pairs-complete-strings-two-set/](https://www.geeksforgeeks.org/python-set-pairs-complete-strings-two-sets/)

如果两个字符串串联在一起，它们包含所有 26 个英文字母，则称为完整字符串。例如，“abcdefghi”和“jklmnopqrstuvwxyz”是完整的，因为它们一起具有从“a”到“z”的所有字符。
我们分别得到两组大小为 n 和 m 的字符串，我们需要找到将集合 1 中的每一个字符串连接到集合 2 中的每一个字符串时完成的对的数量。

示例:

```py
Input : set1[] = {"abcdefgh", "geeksforgeeks",
                 "lmnopqrst", "abc"}
        set2[] = {"ijklmnopqrstuvwxyz", 
                 "abcdefghijklmnopqrstuvwxyz", 
                 "defghijklmnopqrstuvwxyz"} 
Output : 7
The total complete pairs that are forming are:
"abcdefghijklmnopqrstuvwxyz"
"abcdefghabcdefghijklmnopqrstuvwxyz"
"abcdefghdefghijklmnopqrstuvwxyz"
"geeksforgeeksabcdefghijklmnopqrstuvwxyz"
"lmnopqrstabcdefghijklmnopqrstuvwxyz"
"abcabcdefghijklmnopqrstuvwxyz"
"abcdefghijklmnopqrstuvwxyz"

```

对于这个问题我们已经有了解决方案，请参考两组弦链接中的[对完整弦。我们可以使用](https://www.geeksforgeeks.org/pairs-of-complete-strings-in-two-sets-of-strings/)[设置数据结构](https://www.geeksforgeeks.org/sets-in-python/)在 python 中快速解决这个问题。方法很简单，

1.  考虑所有字符串对，逐个连接它们，并将其转换为集合。
2.  现在一个接一个地将串联字符串中的所有字母添加到集合中。因为集合包含唯一的值，所以如果集合的长度等于 26，这意味着集合包含所有 26 个英文字母。

```py
# Function to find pairs of complete strings
# in two sets of strings

def completePair(set1,set2):

    # consider all pairs of string from
    # set1 and set2
    count = 0
    for str1 in set1:
        for str2 in set2:
            result = str1 + str2

            # push all alphabets of concatenated 
            # string into temporary set
            tmpSet = set([ch for ch in result if (ord(ch)>=ord('a') and ord(ch)<=ord('z'))])
            if len(tmpSet)==26:
                count = count + 1
    print (count)

# Driver program
if __name__ == "__main__":
    set1 = ['abcdefgh', 'geeksforgeeks','lmnopqrst', 'abc']
    set2 = ['ijklmnopqrstuvwxyz', 'abcdefghijklmnopqrstuvwxyz','defghijklmnopqrstuvwxyz']
    completePair(set1,set2)
```

输出:

```py
7

```