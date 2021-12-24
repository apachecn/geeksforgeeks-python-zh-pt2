# Python |第 k 次出现字符时拆分字符串

> 原文:[https://www . geesforgeks . org/python-split-string-on-kth-出现字符/](https://www.geeksforgeeks.org/python-split-string-on-kth-occurrence-of-character/)

拆分的很多问题过去已经处理过了，但是有时候，我们也会遇到这个问题，我们需要在一个字符出现第 Kt 次时拆分字符串。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 split()+join()**
split 和 join 方法可以执行此特定任务。在这种情况下，我们根据字符分割字符串，并根据 K，我们使用嵌套连接方法执行重新连接。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Split string on Kth Occurrence of Character
# Using split() + join()

# initializing string
test_str = "Geeks_for_Geeks_is_best"

# split char
splt_char = "_"

# initializing K
K = 3

# printing original string
print("The original string is : " + str(test_str))

# Using split() + join()
# Split string on Kth Occurrence of Character
temp = test_str.split(splt_char)
res = splt_char.join(temp[:K]), splt_char.join(temp[K:])

# printing result
print("Is list after Kth split is : " + str(list(res)))
```

**Output**

```
The original string is : Geeks_for_Geeks_is_best
Is list after Kth split is : ['Geeks_for_Geeks', 'is_best']
```