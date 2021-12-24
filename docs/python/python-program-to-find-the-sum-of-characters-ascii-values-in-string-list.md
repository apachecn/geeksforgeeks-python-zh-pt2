# Python 程序在字符串列表

中查找字符 ascii 值之和

> 原文:[https://www . geesforgeks . org/python-program-to-find-sum-characters-ascii-values-in-string-list/](https://www.geeksforgeeks.org/python-program-to-find-the-sum-of-characters-ascii-values-in-string-list/)

给定字符串列表，任务是编写一个 Python 程序来计算每个字符的 ASCII 值的和值。

**示例:**

> **输入**:test _ list =[“geeksforgeeks”“teaches”“纪律”]
> **输出**:【133，61，100】
> **解释**:位置字符相加得到所需值。
> 
> **输入**:test _ list =[“geeks forgeeks”，“纪律”]
> **输出**:【133，100】
> **解释**:位置字符相加得到所需值。

**方法一:使用** [**顺序()**](https://www.geeksforgeeks.org/ord-function-python/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们迭代每个字符串中的每个字符，并不断添加位置值以获得其总和。求和后的值会追加到列表的结果中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Characters Positions Summation in String List
# Using ord() + loop

# initializing list
test_list = ["geeksforgeeks",
             "teaches", "us", "discipline"]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:
    ascii_sum = 0

    # getting ascii value sum 
    for ele in sub :
        ascii_sum += (ord(ele) - 96)

    res.append(ascii_sum)

# printing result 
print("Position Summation List : " + str(res))
```

**输出:**

> 原列表为:['geeksforgeeks '，' teaches '，' us '，'纪律']
> 职位合计列表:[133，61，40，100]

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/) **+顺序()**

在这种情况下，我们使用 sum()得到求和，使用 order()得到 ASCII 位置值，列表理解为这个问题提供了一个线性解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Characters Positional Summation in String List
# Using list comprehension + sum() + ord()

# initializing list
test_list = ["geeksforgeeks", "teaches", 
             "us", "discipline"]

# printing original list
print("The original list is : " + str(test_list))

# sum() gets summation, list comprehension
# used to perform task in one line 
res = [sum([ord(ele) - 96 for ele in sub]) for sub in test_list]

# printing result 
print("Positional Summation List : " + str(res))
```

**输出:**

> 原列表为:['geeksforgeeks '，' teaches '，' us '，'纪律']
> 职位合计列表:[133，61，40，100]