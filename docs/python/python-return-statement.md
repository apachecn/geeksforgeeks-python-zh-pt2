# Python 返回语句

> 原文:[https://www.geeksforgeeks.org/python-return-statement/](https://www.geeksforgeeks.org/python-return-statement/)

return 语句用于结束函数调用的执行，并将结果(return 关键字后面的表达式的值)返回给调用者。返回语句之后的语句不会被执行。如果 return 语句没有任何表达式，则返回特殊值 None。
**注意:** Return 语句不能在函数外使用。

**语法:**

```
def fun():
    statements
    .
    .
    return [expression]
```

**示例:**

## 蟒蛇 3

```
# Python program to
# demonstrate return statement

def add(a, b):

    # returning sum of a and b
    return a + b

def is_true(a):

    # returning boolean of a
    return bool(a)

# calling function
res = add(2, 3)
print("Result of add function is {}".format(res))

res = is_true(2<5)
print("\nResult of is_true function is {}".format(res))
```

**输出:**

```
Result of add function is 5

Result of is_true function is True
```

## 返回多个值

在 Python 中，我们可以从一个函数中返回多个值。以下是不同的方法。

*   **使用 Object:** 这类似于 C/C++和 Java，我们可以创建一个类(在 C 中，struct)来保存多个值并返回该类的一个对象。

## 蟒蛇 3

```
# A Python program to return multiple 
# values from a method using class
class Test:
    def __init__(self):
        self.str = "geeksforgeeks"
        self.x = 20  

# This function returns an object of Test
def fun():
    return Test()

# Driver code to test above method
t = fun() 
print(t.str)
print(t.x)
```

*   **输出:**

```
geeksforgeeks
20
```

*   **使用元组:**元组是以逗号分隔的项目序列。它是在有或没有()的情况下创建的。元组是不可变的。[元组](https://www.geeksforgeeks.org/python-tuples/)详见[本](https://www.geeksforgeeks.org/python-tuples/)。

## 蟒蛇 3

```
# A Python program to return multiple 
# values from a method using tuple

# This function returns a tuple
def fun():
    str = "geeksforgeeks"
    x = 20
    return str, x;  # Return tuple, we could also
                    # write (str, x)

# Driver code to test above method
str, x = fun() # Assign returned tuple
print(str)
print(x)
```

*   **输出:**

```
geeksforgeeks
20
```

*   **使用列表:**列表就像使用方括号创建的项目数组。它们不同于数组，因为它们可以包含不同类型的项。列表不同于元组，因为它们是可变的。[列表](https://www.geeksforgeeks.org/python-list/)详见[本](https://www.geeksforgeeks.org/python-list/)。

## 蟒蛇 3

```
# A Python program to return multiple 
# values from a method using list

# This function returns a list
def fun():
    str = "geeksforgeeks"
    x = 20  
    return [str, x];  

# Driver code to test above method
list = fun() 
print(list)
```

*   **输出:**

```
['geeksforgeeks', 20]
```

*   **使用字典:**字典类似于其他语言中的散列或映射。[词典](https://www.geeksforgeeks.org/python-dictionary/)详见[本](https://www.geeksforgeeks.org/python-dictionary/)。

## 蟒蛇 3

```
# A Python program to return multiple 
# values from a method using dictionary

# This function returns a dictionary
def fun():
    d = dict(); 
    d['str'] = "GeeksforGeeks"
    d['x']   = 20
    return d

# Driver code to test above method
d = fun() 
print(d)
```

*   **输出:**

```
{'x': 20, 'str': 'GeeksforGeeks'}
```

## 函数返回另一个函数

在 Python 中，函数是对象，所以我们可以从另一个函数返回一个函数。这是可能的，因为函数在 Python 中被视为第一类对象。要了解更多关于第一类对象[的信息，请点击此处](https://www.geeksforgeeks.org/first-class-functions-python/)。
在下面的例子中，create_adder 函数返回加法器函数。

## 蟒蛇 3

```
# Python program to illustrate functions
# can return another function

def create_adder(x):
    def adder(y):
        return x + y

    return adder

add_15 = create_adder(15)

print("The result is", add_15(10))

# Returning different function
def outer(x):
    return x * 10

def my_func():

    # returning different function
    return outer

# storing the function in res
res = my_func()

print("\nThe result is:", res(10))
```

**输出:**

```
The result is 25

The result is: 100
```