# 用 Python 写自己的 len()

> 原文:[https://www.geeksforgeeks.org/write-len-python/](https://www.geeksforgeeks.org/write-len-python/)

方法 [len()](https://en.wikipedia.org/wiki/Len_(programming)) 根据您传递的参数返回列表中的元素数量或字符串长度。

**不使用 len()如何实现:**T0】

**Python 实现:**

```py
# Function which return length of string
def findLength(string):

    # Initialize count to zero
    count = 0

    # Counting character in a string
    for i in string:
        count+= 1
    # Returning count
    return count

# Driver code
string = "geeksforgeeks"
print(findLength(string))
```

输出:

```py
13

```

本文由 **[萨赫勒拉吉普特](https://www.linkedin.com/in/sahil-rajput-3ba2b3134/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。