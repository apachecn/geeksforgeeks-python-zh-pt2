# 从字符串中删除第 I 个字符的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-for-remove-I-th-character-from-string/](https://www.geeksforgeeks.org/python-program-for-removing-i-th-character-from-a-string/)

给定字符串，我们必须从字符串中移除第 i <sup>个</sup>索引字符。

在任何字符串中，索引总是从 0 开始。假设我们有一个字符串极客，那么它的索引将是–

```
g e e k s
0 1 2 3 4

```

**示例:**

```
Input : Geek
        i = 1
Output : Gek 

Input : Peter 
        i = 4
Output : Pete

```

**方法 1 :** 从给定的字符串中，必须删除第 I 个索引元素。因此，将字符串分成两半，在索引字符之前和索引字符之后。返回合并的字符串。

下面是上述方法的实现:

```
# Python3 program for removing i-th 
# indexed character from a string

# Removes character at index i
def remove(string, i): 

    # Characters before the i-th indexed
    # is stored in a variable a
    a = string[ : i] 

    # Characters after the nth indexed
    # is stored in a variable b
    b = string[i + 1: ]

    # Returning string after removing
    # nth indexed character.
    return a + b

# Driver Code
if __name__ == '__main__':

    string = "geeksFORgeeks"

    # Remove nth index element
    i = 5

    # Print the new string
    print(remove(string, i))
```

**Output:**

```
geeksORgeeks

```

**方法 2 :** 想法是使用 Python 中的[字符串替换
T4】](https://www.geeksforgeeks.org/python-string-replace/)

```
# Python3 program for removing i-th 
# indexed character from a string

# Removes character at index i
def remove(string, i): 

    for j in range(len(string)):
        if j == i:
            string = string.replace(string[i], "", 1)
    return string

# Driver Code
if __name__ == '__main__':

    string = "geeksFORgeeks"

    # Remove nth index element
    i = 5

    # Print the new string
    print(remove(string, i))
```

**Output:**

```
geeksORgeeks

```