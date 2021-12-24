# Python |通过字典作为关键字参数

> 原文:[https://www . geesforgeks . org/python-passing-dictionary-as-key-arguments/](https://www.geeksforgeeks.org/python-passing-dictionary-as-keyword-arguments/)

很多时候，在使用 Python 字典时，由于 OOP 范式的出现，模块化集中在编程的不同方面。因此，可能有很多用例，我们需要将字典作为参数传递给函数。但是这需要将字典键解包为参数，并将它的值解包为参数值。让我们讨论一种可以执行此操作的方法。

**方法:使用 `**` ( splat)运算符**
该运算符用于解包字典，在传入函数时，可以解包字典，并完成将键映射到参数及其值映射到参数值的所需任务。

```py
# Python3 code to demonstrate working of
# Passing dictionary as keyword arguments
# Using ** ( splat ) operator

# Helper function to demo this task
def test_func(a = 4, b = 5):
    print("The value of a is : " + str(a))
    print("The value of b is : " + str(b))

# initializing dictionary
test_dict = {'a' : 1, 'b' : 2}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Testing with default values 
print("The default function call yields : ")
test_func()

print("\r")

# Passing dictionary as keyword arguments
# Using ** ( splat ) operator
print("The function values with splat operator unpacking : ")
test_func(**test_dict)
```

**Output :**

```py
The original dictionary is : {'a': 1, 'b': 2}
The default function call yields : 
The value of a is : 4
The value of b is : 5

The function values with splat operator unpacking : 
The value of a is : 1
The value of b is : 2

```