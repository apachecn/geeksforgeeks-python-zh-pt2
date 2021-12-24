# Python–具有 K 个不同字符的 N 个大小的子字符串

> 原文:[https://www . geesforgeks . org/python-n-size-substrings-with-k-distinct-characters/](https://www.geeksforgeeks.org/python-n-sized-substrings-with-k-distinct-characters/)

给定一个字符串，任务是编写一个 Python 程序来提取 N 个大小并且有 K 个不同字符的字符串。

**示例:**

> **输入**:test _ str = ' geeksforgeicks '，N = 3，K = 2
> **输出** : ['gee '，' eek '，' gee '，' eek '，' gee ']
> **解释** : 3 个长度有 2 个唯一字符被提取。
> 
> **输入**:test _ str = ' geeksforgeicks '，N = 4，K = 2
> **输出** : []
> **解释**:没有 4 长度的字符串，只有 2 个元素。

**方法#1:使用** [**切片**](https://www.geeksforgeeks.org/string-slicing-in-python/) **+** [**设置()**](https://www.geeksforgeeks.org/python-set-method/) **+循环**

在本例中，我们使用切片执行获取 N 个块的任务，set()用于检查唯一元素。循环用于迭代所有可能的块。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# N sized substrings with K distinct characters
# Using slicing + set() + loop

# initializing string
test_str = 'geeksforgeeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing N
N = 3

# initializing K
K = 2

res = []
for idx in range(0, len(test_str) - N + 1):

    # getting unique elements off sliced string
    if (len(set(test_str[idx: idx + N])) == K):
        res.append(test_str[idx: idx + N])

# printing result
print("Extracted Strings : " + str(res))
```

**Output**

```
The original string is : geeksforgeeksforgeeks
Extracted Strings : ['gee', 'eek', 'gee', 'eek', 'gee', 'eek']
```

**方法 2:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**set()**](https://www.geeksforgeeks.org/python-set-method/)**+**[T21】切片](https://www.geeksforgeeks.org/string-slicing-in-python/)

与上述方法类似，唯一的区别是使用列表理解代替循环，只是为了提供解决这个任务的速记。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# N sized substrings with K distinct characters
# Using list comprehension + len() + set() + slicing

# initializing string
test_str = 'geeksforgeeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing N
N = 3

# initializing K
K = 2

# list comprehension used to slice
res = [test_str[idx: idx + N]
       for idx in range(0, len(test_str) - N + 1)
       if len(set(test_str[idx: idx + N])) == K]

# printing result
print("Extracted Strings : " + str(res))
```

**Output**

```
The original string is : geeksforgeeksforgeeks
Extracted Strings : ['gee', 'eek', 'gee', 'eek', 'gee', 'eek']
```