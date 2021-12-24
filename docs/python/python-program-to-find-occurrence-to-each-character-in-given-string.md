# Python 程序，用于查找给定字符串中每个字符的出现位置

> 原文:[https://www . geesforgeks . org/python-program-查找给定字符串中每个字符的出现次数/](https://www.geeksforgeeks.org/python-program-to-find-occurrence-to-each-character-in-given-string/)

给定一个字符串，任务是用 Python 编写一个程序，打印字符串中每个字符的出现次数。

Python 中有多种方法，我们可以完成这个任务。让我们讨论其中的几个。

**方法 1:** 使用`set()` + `count()`

迭代设置转换后的字符串，并获取原始字符串中每个字符的计数。

```py
# Python3 code to program to find occurrence
# to each character in given string

# initializing string 
inp_str = "GeeksforGeeks"

# using set() + count() to get count 
# of each element in string 
out = {x : inp_str.count(x) for x in set(inp_str )} 

# printing result 
print ("Occurrence of all characters in GeeksforGeeks is :\n "+ str(out)) 
```

**Output:**

```py
Occurrence of all characters in GeeksforGeeks is :
 {'o': 1, 'r': 1, 'e': 4, 's': 2, 'f': 1, 'G': 2, 'k': 2}

```

**方法 2:** 使用字典

```py
# Python3 code to program to find occurrence
# to each character in given string

# initializing string 
inp_str = "GeeksforGeeks"

# frequency dictionary
freq = {} 

for ele in inp_str: 
    if ele in freq: 
        freq[ele] += 1
    else: 
        freq[ele] = 1

# printing result  
print ("Occurrence of all characters in GeeksforGeeks is :\n "+ str(freq)) 
```

**Output:**

```py
Occurrence of all characters in GeeksforGeeks is :
 {'e': 4, 'r': 1, 'o': 1, 'f': 1, 'G': 2, 's': 2, 'k': 2}

```

**方法 3:** 使用`collections`

```py
# Python3 code to program to find occurrence
# to each character in given string
from collections import Counter 

# initializing string  
in_str = "GeeksforGeeks"

# using collections.Counter() to get  
# count of each element in string  
oup = Counter(in_str) 

# printing result  
print ("Occurrence of all characters in GeeksforGeeks is :\n "+ str(oup)) 
```

**Output:**

```py
Occurrence of all characters in GeeksforGeeks is :
 Counter({'e': 4, 's': 2, 'G': 2, 'k': 2, 'f': 1, 'r': 1, 'o': 1})

```