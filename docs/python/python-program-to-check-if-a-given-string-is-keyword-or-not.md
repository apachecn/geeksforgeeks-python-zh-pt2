# Python 程序检查给定字符串是否为关键字

> 原文:[https://www . geesforgeks . org/python-program-to-check-如果给定字符串是关键字或不是关键字/](https://www.geeksforgeeks.org/python-program-to-check-if-a-given-string-is-keyword-or-not/)

给定一个字符串，编写一个 Python 程序，检查给定的字符串是否是关键字。

*   关键字是不能用作变量名的保留字。
*   Python 编程语言中有 33 个关键词。(在 python 3.6.2 版本中)

**示例:**

```
Input: str = "geeks"
Output: geeks is not a keyword

Input: str = "for"
Output: for is a keyword

```

我们总是可以在关键字模块中使用`kwlist` 方法得到当前 Python 版本的关键字列表。

```
# import keyword library
import keyword

keyword_list = keyword.kwlist
print("No. of keywords present in current version :",
                                   len(keyword_list))

print(keyword_list)
```

**Output:**

> 当前版本中存在的关键字数量:33
> ['False '，' None '，' True '，' and '，' as '，' assert '，' break '，' class '，' continue '，' def '，' del '，' elif '，' else '，' except '，' finally '，' for '，' from '，' global '，' if '，' import '，' in '，' is '，' lambda '，'非本地'，' not '，' or '

下面是检查给定字符串是否为关键字的 Python 代码:

```
# include keyword library in this program
import keyword

# Function to check whether the given 
# string is a keyword or not 
def isKeyword(word) :

    # kwlist attribute of keyword
    # library return list of keywords
    # present in current version of
    # python language.
    keyword_list = keyword.kwlist

    # check word in present in
    # keyword_list or not.
    if word in keyword_list :
        return "Yes"
    else :
        return "No"

# Driver Code
if __name__ == "__main__" :

    print(isKeyword("geeks"))
    print(isKeyword("for"))
```

**Output:**

```
No
Yes

```