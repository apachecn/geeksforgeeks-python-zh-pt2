# Python |根据第 n 个元组元素替换元组

> 原文:[https://www . geesforgeks . org/python-replace-tuple-根据第 n 个 tuple-element/](https://www.geeksforgeeks.org/python-replace-tuple-according-to-nth-tuple-element/)

有时，在处理数据时，我们可能会遇到一个问题，即需要替换与特定数据条目相匹配的条目。这可以是匹配的电话号码，身份证等。这就有了它在 web 开发领域的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `enumerate()`**
这个任务可以使用循环和枚举函数的组合来执行，这有助于访问第 n 个元素，然后在条件满足时进行检查和替换。

```py
# Python3 code to demonstrate working of
# Replace tuple according to Nth tuple element
# Using loops + enumerate()

# Initializing list
test_list = [('gfg', 1), ('was', 2), ('best', 3)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing change record
repl_rec = ('is', 2)

# Initializing N 
N = 1

# Replace tuple according to Nth tuple element
# Using loops + enumerate()
for key, val in enumerate(test_list):
    if val[N] == repl_rec[N]:
        test_list[key] = repl_rec
        break

# printing result
print("The tuple after replacement is : " + str(test_list))
```

**Output :**

```py
The original list is : [('gfg', 1), ('was', 2), ('best', 3)]
The tuple after replacement is : [('gfg', 1), ('is', 2), ('best', 3)]

```