# Python 程序对反串对进行计数

> 原文:[https://www . geesforgeks . org/python-程序对反向字符串对进行计数/](https://www.geeksforgeeks.org/python-program-to-count-the-pairs-of-reverse-strings/)

给定字符串列表，编写一个 Python 程序来计数成对的反向字符串。

**示例:**

> **输入** : test_list = [“极客”、“最佳”、“tseb”、“for”、“skeg”]
> **输出** : 2
> **说明**:极客、skeg 和最佳、tseb 均为 2 对反向弦可用。
> 
> **输入** : test_list = [“极客”、“最佳”、“适合”、“斯基格”]
> **输出** : 1
> **说明**:极客、斯基格有 1 对反弦可用。

**方法#1:使用** [**反转()**](https://www.geeksforgeeks.org/python-reversed-function/) **+循环**

在本例中，我们使用 [reversed()](https://www.geeksforgeeks.org/python-reversed-function/) 和条件语句来执行将字符串与它的反向版本进行比较的任务。在这种情况下，循环用于与配对的每个字符串进行比较的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Reversed Pairs in Strings List
# Using reversed() + loop

# initializing Matrix
test_list = ["geeks", "best", "tseb", "for", "skeeg"]

# printing original list
print("The original list is : " + str(test_list))

res = 0
for idx in range(0, len(test_list)):

    # nested loop to check with each element with possible reverse counterpart
    for idxn in range(idx, len(test_list)):
        if test_list[idxn] == str(''.join(list(reversed(test_list[idx])))):
            res += 1

# printing result
print("Reversed Pairs : " + str(res))
```

**输出:**

> 最初的名单是:['极客'，'最佳'，' tseb '，' for '，' skeg ']
> 反向配对:2

**方法二:使用列表理解+** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/)

在这种情况下，列表理解处理嵌套循环，sum()处理计数对的增量计数器的一部分。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Reversed Pairs in Strings List
# Using list comprehension + sum()

# initializing Matrix
test_list = ["geeks", "best", "tseb", "for", "skeeg"]

# printing original list
print("The original list is : " + str(test_list))

# list comprehension for nested loop
# sum increments counts
res = sum([1 for idx in range(0, len(test_list)) for idxn in range(idx, len(
    test_list)) if test_list[idxn] == str(''.join(list(reversed(test_list[idx]))))])

# printing result
print("Reversed Pairs : " + str(res))
```

**输出:**

> 最初的名单是:['极客'，'最佳'，' tseb '，' for '，' skeg ']
> 反向配对:2