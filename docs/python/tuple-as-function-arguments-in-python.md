# Python 中作为函数参数的元组

> 原文:[https://www . geesforgeks . org/tuple-as-function-arguments-in-python/](https://www.geeksforgeeks.org/tuple-as-function-arguments-in-python/)

元组在 Python 编程的所有领域中都有许多应用。它们是不可变的，因此是重要的容器，可以确保只读访问，或者将元素保持更长时间。通常，它们可以用来传递给函数，并且可以有不同种类的行为。可能会出现不同的情况。

> **情况 1:** fnc(a，b)–将 a 和 b 作为单独的元素发送给 fnc。
> 
> **情况 2:** fnc((a，b))–发送(a，b)，整个元组作为一个单一实体，一个元素。
> 
> **情况 3:** fnc(*(a，b))–像情况 1 一样，将 a 和 b 作为单独的整数发送。

下面的代码演示了所有情况下的工作方式:

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Tuple as function arguments

# function with default arguments 
def fnc(a=None, b=None):
    print("Value of a : " + str(a))
    print("Value of b : " + str(b))

# Driver code
if __name__ == "__main__" :

  # initializing a And b
  a = 4
  b = 7

  # Tuple as function arguments
  # Case 1 - passing as integers
  print("The result of Case 1 : ")
  fnc(a, b)

  # Tuple as function arguments
  # Case 2 - Passing as tuple
  print("The result of Case 2 : ")
  fnc((a, b))

  # Tuple as function arguments
  # Case 3 - passing as pack/unpack 
  # operator, as integer
  print("The result of Case 3 : ")
  fnc(*(a, b))
```

**输出:**

```py
The result of Case 1 : 
Value of a : 4
Value of b : 7
The result of Case 2 : 
Value of a : (4, 7)
Value of b : None
The result of Case 3 : 
Value of a : 4
Value of b : 7

```