# Python |使用 ordereddct()

检查字符串中的字符顺序

> 原文:[https://www . geeksforgeeks . org/using-ordereddct-python-check-order-characters-string/](https://www.geeksforgeeks.org/using-ordereddict-python-check-order-characters-string/)

给定输入字符串和模式，检查输入字符串中的字符是否遵循由模式中的字符确定的相同顺序。假设模式中没有任何重复的字符。

示例:

```py
Input: 
string = "engineers rock"
pattern = "er";
Output: true
Explanation: 
All 'e' in the input string are before all 'r'.

Input: 
string = "engineers rock"
pattern = "egr";
Output: false
Explanation: 
There are two 'e' after 'g' in the input string.

Input: 
string = "engineers rock"
pattern = "gsr";
Output: false
Explanation:
There are one 'r' before 's' in the input string.

```

这个问题我们已经有了解决方案，请参考[检查字符串是否遵循模式定义的字符顺序|设置 1](https://www.geeksforgeeks.org/check-string-follows-order-characters-defined-pattern-not/) 。这里我们使用[ordereddct()](https://www.geeksforgeeks.org/remove-duplicates-given-string-python/)在 python 中快速解决这个问题。方法很简单，

*   Create an OrderedDict of the input string, which contains only the characters of the input string as the **key** .
*   Now set a pointer at the beginning of the pattern string.
*   Now traverse the generated OrderedDict and match the key with a single character of the pattern string. If the key and character match each other, increase the pointer by 1.
*   If the pointer of the pattern reaches its end, it means that the string follows the character order defined by the pattern, otherwise it does not.

```py
# Function to check if string follows order of 
# characters defined by a pattern 
from collections import OrderedDict 

def checkOrder(input, pattern): 

    # create empty OrderedDict 
    # output will be like {'a': None,'b': None, 'c': None} 
    dict = OrderedDict.fromkeys(input) 

    # traverse generated OrderedDict parallel with 
    # pattern string to check if order of characters 
    # are same or not 
    ptrlen = 0
    for key,value in dict.items(): 
        if (key == pattern[ptrlen]): 
            ptrlen = ptrlen + 1

        # check if we have traverse complete 
        # pattern string 
        if (ptrlen == (len(pattern))): 
            return 'true'

    # if we come out from for loop that means 
    # order was mismatched 
    return 'false'

# Driver program 
if __name__ == "__main__": 
    input = 'engineers rock'
    pattern = 'egr'
    print (checkOrder(input,pattern)) 
```

输出:

```py
true

```

本文由 [**沙莎克·米什拉(古卢)**](https://auth.geeksforgeeks.org/profile.php?user=Shashank Mishra) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。