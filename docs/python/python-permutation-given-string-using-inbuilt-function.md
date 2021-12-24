# Python |使用内置函数对给定字符串进行置换

> 原文:[https://www . geesforgeks . org/python-排列-给定-字符串-使用-内置-函数/](https://www.geeksforgeeks.org/python-permutation-given-string-using-inbuilt-function/)

排列，也称为“排列数”或“顺序”，是将有序列表 S 的元素重新排列成与 S 本身一一对应的关系。长度为 n 的字符串有 n！排列。

示例:

```py
Input :  str = 'ABC'
Output : ABC 
         ACB 
         BAC 
         BCA 
         CAB 
         CBA
```

我们已经有了这个问题的解决方案，请参考使用 STL 链接给定字符串的[排列。我们也可以使用内置函数](https://www.geeksforgeeks.org/permutations-of-a-given-string-using-stl/)[置换(可迭代)](https://www.geeksforgeeks.org/permutation-and-combination-in-python/)在 python 中解决这个问题。

```py
# Function to find permutations of a given string
from itertools import permutations

def allPermutations(str):

     # Get all permutations of string 'ABC'
     permList = permutations(str)

     # print all permutations
     for perm in list(permList):
         print (''.join(perm))

# Driver program
if __name__ == "__main__":
    str = 'ABC'
    allPermutations(str)
```

**Output:**

```py
ABC
ACB
BAC
BCA
CAB
CBA

```

[Python 中的排列组合](https://www.geeksforgeeks.org/permutation-and-combination-in-python/)

**给定字符串与重复字符的排列**
这个想法是使用字典来避免重复打印。

```py
from itertools import permutations
import string

s = "GEEK"
a = string.ascii_letters
p = permutations(s)

# Create a dictionary
d = []
for i in list(p):

    # Print only if not in dictionary
    if (i not in d):
        d.append(i)
        print(''.join(i))
```

**Output:**

```py
GEEK
GEKE
GKEE
EGEK
EGKE
EEGK
EEKG
EKGE
EKEG
KGEE
KEGE
KEEG

```