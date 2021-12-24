# Python 程序将给定字符大写

> 原文:[https://www . geesforgeks . org/python-程序-大写字母/](https://www.geeksforgeeks.org/python-program-to-uppercase-the-given-characters/)

给定一个字符串和一组字符，将字符串中出现的所有字符转换为大写()

> **输入** : test_str = 'gfg 最适合极客'，upper_list = ['g '，' e '，' b']
> **输出** : GfG 最适合极客
> **解释**:只增加了选择性字符。
> 
> **输入** : test_str = 'gfg 为最佳'，upper_list = ['g '，' e '，' b']
> **输出** : GfG 为最佳
> **解释**:只增加了选择性字符。

**方法#1:使用 loop + upper()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用循环检查每个字符，如果它在字符中，则使用大写()将其转换为大写。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Uppercase custom characters
# Using upper() + loop

# initializing string
test_str = 'gfg is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing upperlist 
upper_list = ['g', 'e', 'b', 'k']

res = ''
for ele in test_str:

    # checking for presence in upper list 
    if ele in upper_list:
        res += ele.upper()
    else :
        res += ele

# printing result 
print("String after reconstruction : " + str(res))
```

**Output**

```
The original string is : gfg is best for geeks
String after reconstruction : GfG is BEst for GEEKs

```

**方法 2:使用列表理解**

这是执行这项任务的另一种方式。在这种情况下，我们以与上述方法类似的方式执行任务，但使用单行列表理解作为速记。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Uppercase custom characters
# Using list comprehension

# initializing string
test_str = 'gfg is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing upperlist 
upper_list = ['g', 'e', 'b', 'k']

# one-liner used to solve problem
res = "".join([ele.upper() if ele in upper_list else ele for ele in test_str])

# printing result 
print("String after reconstruction : " + str(res))
```

**Output**

```
The original string is : gfg is best for geeks
String after reconstruction : GfG is BEst for GEEKs

```