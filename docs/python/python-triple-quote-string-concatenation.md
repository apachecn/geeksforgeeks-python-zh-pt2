# Python–三引号字符串串联

> 原文:[https://www . geesforgeks . org/python-三引号-字符串-串联/](https://www.geeksforgeeks.org/python-triple-quote-string-concatenation/)

有时，在使用 Python 字符串时，我们可能会遇到这样的问题，即我们需要执行由三重引号构造的字符串串联。这发生在我们有多行字符串的情况下。这在许多领域都有应用。让我们讨论执行这项任务的特定方式。

```
Input : test_str1 = """mango
is"""
test_str2 = """good
for health
"""
Output : mango good
 is for health

Input : test_str1 = """Gold
is"""
test_str2 = """important
for economy
"""
Output : Gold important
 is for economy

```

**方法:使用`splitlines() + strip() + join()`**
以上功能的组合可以用来执行此任务。在本例中，我们使用`splitlines()`执行行分割的任务。使用`strip()`和`join()`完成串联任务。

```
# Python3 code to demonstrate working of 
# Triple quote String concatenation
# Using splitlines() + join() + strip()

# initializing strings
test_str1 = """gfg
is"""
test_str2 = """best
for geeks
"""

# printing original strings
print("The original string 1 is : " + test_str1)
print("The original string 2 is : " + test_str2)

# Triple quote String concatenation
# Using splitlines() + join() + strip()
test_str1 = test_str1.splitlines()
test_str2 = test_str2.splitlines()
res = []

for i, j in zip(test_str1, test_str2):
    res.append("   " + i.strip() + " " + j.strip())
res = '\n'.join(res)

# printing result 
print("String after concatenation : " + str(res)) 
```

**Output :**

```
The original string 1 is : gfg
is
The original string 2 is : best
for geeks

String after concatenation :    gfg best
   is for geeks

```