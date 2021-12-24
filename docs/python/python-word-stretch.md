# Python |单词拉伸

> 原文:[https://www.geeksforgeeks.org/python-word-stretch/](https://www.geeksforgeeks.org/python-word-stretch/)

编写一个程序，获取将一个单词扩展到给定大小的所有可能性(按排序顺序)。如果所需索引的列表被通过，那么应该只返回那些索引处的那些组合。如果所需的索引为空，则必须返回所有组合。
**例:**

```
Input:
str = "1234"  
n = 6 
indices = null 

Output: 
["111234", "112234", "112334", "112344", "122234",
 "122334", "122344", "123334", "123344", "123444"] 

The above string  “1234”, with stretch length can be stretched for different possibilities
like "111234", "112334", "112344" etc. The output represents a list of 
different stretches in a sorted manner. Since the indices are given as
null we print the entire list of possibilities 

Input: 
str = "1234"
n = 6 
indices = 1, 5, 9 
Output: 
["112234", "122334", "123444"]

Here only stretched strings of given indices are printed. 

Input: 
str = "merit"  
n = 6 
indices = null 
Output: 
["meerit", "meriit", "meritt", "merrit", "mmerit"] 

Input: 
str = "java"  
n = 4 
indices = null 
Output: ["java"] 

Input : 
str = "geeksforgeeks"
n = 10 
indices = null 
Output: 
[] 

since the length of the string is greater than 
the length to be stretched we return an empty index
```

**代码:Python 代码，用于获取将单词拉伸到给定大小的所有可能性。**

## 蟒蛇 3

```
# function which stretches the word

def WordStretch(s, n, indices) :
    res, index, result, final = [], [], [], []

    # check for corner case
    if n < len(s) :
        print([])

    # check for corner case

    elif n == len(s) :
        print([s])

    else :

        # since the word should be stretched
        # to n terms which include the length
        temp = n-len(s)

        for i in range(len(s)):
            for j in range(i, len(s)):

                if i == j :
                    l = temp * s[j]
                    m = s[:j] + l + s[j:]
                    result.append(m)

                else :
                    l = (temp-1) * s[j]
                    m = s[:j] + l + s[j:]
                    # here we convert the string into list
                    # and again list into string after inserting
                    # the element in the list
                    t =[]
                    for p in m :
                        t.append(p)
                    t.insert(i, s[i])
                    result.append("".join(t))

        # to sort the elements
        result.sort()

        # to remove the duplicate elements

        for i in result :
            if i not in final :
                final.append(i)

        # to print the entire list       
        if indices == 'null' :
            print(result)

        # to print particular indices   
        else :      
            index = list(map(int, indices.split()))
            for i in index :
                res.append(final[i])
            print(res)

# drive code
s = "1234"
n = 6
x = "null"
WordStretch(s, n, x)
```

**输出:**

```
['111234', '112234', '112334', '112344', '122234', 
'122334', '122344', '123334', '123344', '123444']
```