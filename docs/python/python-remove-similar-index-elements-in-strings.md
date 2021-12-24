# Python–删除字符串中类似的索引元素

> 原文:[https://www . geesforgeks . org/python-remove-相似-索引-字符串中的元素/](https://www.geeksforgeeks.org/python-remove-similar-index-elements-in-strings/)

给定两个字符串，从两个字符串中移除所有在相似索引处相同的元素。

> **输入** : test_str1 = 'geels '，test_str2 = 'beaks'
> **输出**:凝胶，bak
> **解释** : e 和 s 在相同的索引中出现时被移除。
> 
> **输入** : test_str1 = '极客'，test_str2 = '极客'
> **输出**:、“
> **解释**:相同的字符串，都是相同的索引，因此被删除。

**方法#1:使用 loop + zip() + join()**

在本文中，我们使用 join()将元素与其索引配对，并检查不等式以仅过滤两个字符串中不相似的元素，join()用于转换字符串中的结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove similar index elements in Strings
# Using join() + zip() + loop

# initializing strings
test_str1 = 'geeks'
test_str2 = 'beaks'

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# conversion to list for zipping
list1 = list(test_str1)
list2 = list(test_str2)
res1 = []
res2 = []
for ch1, ch2 in zip(list1, list2):

    # check inequalities
    if ch1 != ch2:
        res1.append(ch1)
        res2.append(ch2)

# conversion to string 
res1 = "".join(res1)
res2 = "".join(res2)

# printing result 
print("Modified String 1 : " + str(res1)) 
print("Modified String 2 : " + str(res2)) 
```

**Output**

```py
The original string 1 is : geeks
The original string 2 is : beaks
Modified String 1 : ge
Modified String 2 : ba

```

**方法 2:使用列表理解**

使用与上面类似的方法执行任务，只是一行代码以紧凑的形式执行任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove similar index elements in Strings
# Using list comprehension

# initializing strings
test_str1 = 'geeks'
test_str2 = 'beaks'

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# one-liner to solve problem
res = ["".join(mastr) for mastr
      in zip(*[(a, b) for a, b in zip(test_str1, test_str2) if a != b])]

# printing result 
print("Modified String 1 : " + str(res[0])) 
print("Modified String 2 : " + str(res[1])) 
```

**Output**

```py
The original string 1 is : geeks
The original string 2 is : beaks
Modified String 1 : ge
Modified String 2 : ba

```