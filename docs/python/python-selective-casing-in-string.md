# Python |字符串中的选择性套管

> 原文:[https://www . geesforgeks . org/python-选择性套管柱/](https://www.geeksforgeeks.org/python-selective-casing-in-string/)

有时，在使用 Python 时，我们可能会遇到一个问题，需要对字符串中的某些字符进行大小写更改。这种问题可能出现在许多类型的应用中。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`enumerate() + loop + upper()`**
这个问题可以使用上面的一组功能来解决。这是一种暴力的方式来执行这个任务，在这种情况下，我们遍历字符串中的每个元素，如果它出现在大小写改变列表中，就将其改为大写。

```
# Python3 code to demonstrate working of
# Selective casing in String
# using loop + upper() + enumerate()

# initialize string
test_str = 'gfg is best'

# printing original string 
print("The original string : " + str(test_str))

# initialize change case list 
chg_list = ['g', 'f', 's']

# Selective casing in String
# using loop + upper() + enumerate()
res = list(test_str)
for idx, char in enumerate(res):
    if char in chg_list:
        res[idx] = char.upper()

# printing result
print("String after Selective casing : " + str(''.join(res)))
```

**Output :**

```
The original string : gfg is best
String after Selective casing : GFG iS beSt

```