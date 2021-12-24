# 在 Python 中反转给定字符串中的单词

> 原文:[https://www . geesforgeks . org/reverse-words-given-string-python/](https://www.geeksforgeeks.org/reverse-words-given-string-python/)

给我们一个字符串，我们需要反转给定字符串的单词？

示例:

```
Input : str = geeks quiz practice code
Output : str = code practice quiz geeks

```

此问题已有解决方案请参考[给定字符串中的反向单词](https://www.geeksforgeeks.org/reverse-words-in-a-given-string/)链接。我们将用 python 解决这个问题。下面给出了解决这个问题应遵循的步骤。

*   Use the [split ()](https://www.geeksforgeeks.org/how-to-split-a-string-in-cc-python-and-java/) method of string data type in python to separate each word in a given string.
*   Invert the word separated list.
*   Print the words in the list, connect each word with a space in the form of a string and use ["". Join ()](https://www.geeksforgeeks.org/python-string-methods-set-2-len-count-center-ljust-rjust-isalpha-isalnum-isspace-join/) method in python.

```
# Function to reverse words of string 

def rev_sentence(sentence): 

    # first split the string into words 
    words = sentence.split(' ') 

    # then reverse the split string list and join using space 
    reverse_sentence = ' '.join(reversed(words)) 

    # finally return the joined string 
    return reverse_sentence 

if __name__ == "__main__": 
    input = 'geeks quiz practice code'
    print (rev_sentence(input))
```

输出:

```
code practice quiz geeks

```

本文由 [**沙莎克·米什拉(古卢)**](https://auth.geeksforgeeks.org/profile.php?user=Shashank Mishra) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。