# Python |使用另一个字符串定义的顺序对字符串进行排序

> 原文:[https://www . geesforgeks . org/python-排序-字符串-使用顺序-由另一个字符串定义/](https://www.geeksforgeeks.org/python-sorting-string-using-order-defined-by-another-string/)

给定两个字符串(小写字母)，一个模式和一个字符串。任务是根据模式定义的顺序对字符串进行排序，并返回相反的顺序。可以假设模式具有字符串的所有字符，并且模式中的所有字符只出现一次。

**示例:**

```
Input : pat = "asbcklfdmegnot", str = "eksge" 
Output : str = "geeks"
(after sorting, str becomes "skeeg" and return its reverse)

Input : pat = "mgewqnasibkldjxruohypzcftv", str = "niocgd"
Output : str = "coding"

```

其思想是首先根据 Pattern 中提供的索引维护一个字典，然后将 lambda 函数(使用字典的效用)传递给 sort 函数。
下面是上面思路的实现。

```
# Python program to sort a string and return
# its reverse string according to pattern string

# This function will return the reverse of sorted string
# according to the pattern

def sortbyPattern(pat, str):

    priority = list(pat)

    # Create a dictionary to store priority of each character
    myDict = { priority[i] : i for i in range(len(priority))}

    str = list(str)

    # Pass lambda function as key in sort function
    str.sort( key = lambda ele : myDict[ele])

    # Reverse the string using reverse()
    str.reverse()

    new_str = ''.join(str)
    return new_str

if __name__=='__main__':
    pat = "asbcklfdmegnot"
    str =  "eksge"
    new_str = sortbyPattern(pat, str)
    print(new_str)
```

**输出:**

```
geeks
```

**时间复杂度:** n*log(n)，其中 n 是字符串的长度