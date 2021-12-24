# Python–按自定义长度拆分字符串

> 原文:[https://www . geesforgeks . org/python-按自定义长度拆分字符串/](https://www.geeksforgeeks.org/python-split-a-string-by-custom-lengths/)

给定一个字符串，根据自定义长度执行字符串拆分。

> **输入** : test_str = 'geeksforgeeks '，cus_lens = [4，3，2，3，1]
> **输出** : ['geek '，' sfo '，' rg '，' eek '，' s']
> **解释**:由自定义长度分隔的字符串。
> **输入**:test _ str = ' geesforgeks '，cus_lens = [10，3]
> **输出**:[' geesforge '，' eks']
> **解释**:由自定义长度分隔的字符串。

**方法#1:使用切片+循环**

在这种情况下，我们执行切片任务来迎合定制长度，并使用循环来迭代所有长度。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Multilength String Split
# Using loop + slicing

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing length list
cus_lens = [5, 3, 2, 3]

res = []
strt = 0
for size in cus_lens:

    # slicing for particular length
    res.append(test_str[strt : strt + size])
    strt += size

# printing result 
print("Strings after splitting : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks
Strings after splitting : ['geeks', 'for', 'ge', 'eks']

```

**方法 2:使用 join() +列表理解+ next()**

这是执行这项任务的另一种方式。在这种情况下，我们使用 next()迭代器方法执行获取字符直到长度的任务，提供了更有效的解决方案。最后，join()用于将每个字符列表转换为字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Multilength String Split
# Using join() + list comprehension + next()

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing length list
cus_lens = [5, 3, 2, 3]

# join() performs characters to string conversion
# list comprehension provides shorthand to solve problem
stritr = iter(test_str)
res = ["".join(next(stritr) for idx in range(size)) for size in cus_lens]

# printing result 
print("Strings after splitting : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks
Strings after splitting : ['geeks', 'for', 'ge', 'eks']

```