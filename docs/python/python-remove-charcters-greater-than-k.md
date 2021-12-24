# Python–删除大于 K 的字符

> 原文:[https://www . geesforgeks . org/python-remove-characters-大于-k/](https://www.geeksforgeeks.org/python-remove-charcters-greater-than-k/)

给定字符串列表，从每个字符串中删除字符大于 k 的所有字符

> **输入**:test _ list =[“geeksforgeeks”，“is”，“best”，“for”，“geeks”]，K = 13
> **输出**:[‘geekfgeek’，‘I’，‘be’，‘f’，‘geek’]
> **解释**:去掉 m 以上 ASCII 字符。
> 
> **输入**:test _ list =[“geeksforgeeks”，“is”，“best”，“for”，“geeks”]，K = 10
> **输出**:[‘geekfgeek’，‘I’，‘be’，‘f’，‘geek’]
> **解释**:去掉 j 上面的 ASCII 字符。

**方法#1:使用循环+顺序()**

在这种情况下，我们使用 order()检查字符的 ASCII 值，然后与 K 进行比较，如果字符大于 K，则该字符不包括在结果字符串中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove characters greater than K
# Using loop + ord()

# initializing list
test_list = ["geeksforgeeks", "is", "best", "for", "geeks"]

# printing original lists
print("The original list is : " + str(test_list))

# initializing K
K = 13

res = []
for ele in test_list:
    res_str = ''
    for sub in ele:

        # check for string characters
        if (ord(sub) - 97 <= K):
            res_str += sub
    res.append(res_str)

# printing result
print("Filtered List " + str(res))
```

**输出:**

> 原列表为:['geeksforgeeks '，' is '，' best '，' for '，' geeks']
> 过滤列表['geekfgeek '，' I '，' be '，' f '，' geek']

**方法 2:使用 join() +列表理解+order()**

这是执行这项任务的一种简便方法。在本文中，我们使用 join()执行过滤和连接以形成字符串的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove characters greater than K
# Using join() + list comprehension + ord()

# initializing list
test_list = ["geeksforgeeks", "is", "best", "for", "geeks"]

# printing original lists
print("The original list is : " + str(test_list))

# initializing K
K = 13

# using list comprehension for 1 liner
res = [''.join([ele for ele in sub if ord(ele) - 97 <= K]) for sub in test_list]

# printing result
print("Filtered List " + str(res))
```

**输出:**

> 原列表为:['geeksforgeeks '，' is '，' best '，' for '，' geeks']
> 过滤列表['geekfgeek '，' I '，' be '，' f '，' geek']