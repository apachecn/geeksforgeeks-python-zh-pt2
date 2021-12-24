# Python 函数名中允许的字符有哪些？

> 原文:[https://www . geesforgeks . org/python 中允许的字符是什么-函数名/](https://www.geeksforgeeks.org/what-are-the-allowed-characters-in-python-function-names/)

赋予函数或变量的用户定义名称称为标识符。它有助于区分一个实体与另一个实体，有时也作为该实体使用的定义。正如在每种编程语言中一样，标识符也有一些限制。因此，对于 Python 来说，在使用标识符之前，我们需要注意以下几点。

**编写标识符的规则:**

*   The first limitation is that the identifier cannot be the same as the [keyword](https://www.geeksforgeeks.org/keywords-python-set-1/) . Each programming language has special reserved keywords, which have their own meanings. These names cannot be used as identifiers in Python.

## 蟒 3

```
# Python program to demonstrate
# that keywords cant be used as
# identifiers

def calculate_sum(a, b):
  return a + b

x = 2
y = 5
print(calculate_sum(x,y))

# def and if is a keyword, so
# this would give invalid
# syntax error
def = 12  
if = 2     

print(calculate_sum(def, if))
```