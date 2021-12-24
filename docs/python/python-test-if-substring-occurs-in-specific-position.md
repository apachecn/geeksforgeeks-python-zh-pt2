# Python–测试子串是否出现在特定位置

> 原文:[https://www . geesforgeks . org/python-test-if-substring-occurs-in-specific-position/](https://www.geeksforgeeks.org/python-test-if-substring-occurs-in-specific-position/)

有时，在使用 python 字符串时，我们会遇到一个问题，需要测试子字符串的出现。有一个直接的方法来测试这一点。但是有时候，我们有一个更具体的问题，我们需要测试子串是否出现在那个特定的位置。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是解决这个问题的蛮法。在这种情况下，我们迭代字符串，当索引出现时，我们同时测试子字符串字符。

```py
# Python3 code to demonstrate working of 
# Test if Substring occurs in specific position
# Using loop

# initializing string 
test_str = "Gfg is best"

# printing original string 
print("The original string is : " + test_str)

# initializing range 
i, j = 7, 11

# initializing substr
substr = "best"

# Test if Substring occurs in specific position
# Using loop
res = True
k = 0
for idx in range(len(test_str)):
    if idx >= i  and idx < j:
        if test_str[idx] != substr[k]:
            res = False
            break
        k = k + 1

# printing result 
print("Does string contain substring at required position ? : " + str(res)) 
```

**Output :**

```py
The original string is : Gfg is best
Does string contain substring at required position ? : True

```