# Python 属性装饰器–@属性

> 原文:[https://www . geesforgeks . org/python-property-decorator-property/](https://www.geeksforgeeks.org/python-property-decorator-property/)

Python 中的一个[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)特性包装了一个函数，将几个功能附加到现有代码中，然后返回它。众所周知，方法和函数是可调用的，因为它们可以被调用。因此，装饰器也是返回可调用的可调用的。这也被称为**元编程**，因为在编译时，程序的一部分会改变程序的另一部分。

**注意:**更多信息请参考 Python 中的[装饰者](https://www.geeksforgeeks.org/decorators-in-python/)

## Python @property decorator

`@property` decorator 是 Python 中的内置 decorator，它有助于轻松定义属性，而无需手动调用内置函数 [property()](https://www.geeksforgeeks.org/python-property-function/) 。它用于从指定的 getter、setter 和 deleter 返回类的属性属性作为参数。

**现在，让我们看一些例子来说明 Python 中 **@property** 装饰器的使用:**
**例子 1:**

```
# Python program to illustrate the use of
# @property decorator

# Defining class
class Portal:

    # Defining __init__ method
    def __init__(self):
        self.__name =''

    # Using @property decorator
    @property

    # Getter method
    def name(self):
        return self.__name

    # Setter method
    @name.setter
    def name(self, val):
        self.__name = val

    # Deleter method
    @name.deleter
    def name(self):
       del self.__name

# Creating object
p = Portal();

# Setting name
p.name = 'GeeksforGeeks'

# Prints name
print (p.name)

# Deletes name
del p.name

# As name is deleted above this 
# will throw an error
print (p.name)
```

**Output:**

```
GeeksforGeeks

## An error is thrown
Traceback (most recent call last):
  File "main.py", line 42, in 
    print (p.name)
  File "main.py", line 16, in name
    return self.__name
AttributeError: 'Portal' object has no attribute '_Portal__name'

```

这里，@property decorator 用于定义类`Portal`中的属性`name`，该类有三个名称相似的方法(getter、setter 和 deleter)，即`name()`，但它们的参数数量不同。其中，标有`@property`的方法**名称(self)** 是一个 getter 方法，**名称(self，val)** 是一个 setter 方法，因为它用于设置属性**_ _ 名称**的值，所以它标有`@name.setter`。最后，标有 *@name.deleter* 的方法是一个 deleter 方法，可以通过 setter 方法删除赋值。但是，deleter 是在关键字`del`的帮助下调用的。
**例 2:**

```
# Python program to illustrate the use of
# @property decorator

# Creating class
class Celsius:

    # Defining init method with its parameter
    def __init__(self, temp = 0):
        self._temperature = temp

    # @property decorator
    @property

    # Getter method
    def temp(self):

        # Prints the assigned temperature value
        print("The value of the temperature is: ")
        return self._temperature

    # Setter method
    @temp.setter
    def temp(self, val):

        # If temperature is less than -273 than a value
        # error is thrown
        if val < -273:
            raise ValueError("It is a value error.")

        # Prints this if the value of the temperature is set
        print("The value of the tempereture is set.")
        self._temperature = val

# Creating object for the stated class 
cel = Celsius();

# Setting the temperature value
cel.temp = -270

# Prints the temperature that is set
print(cel.temp)

# Setting the temperature value to -300
# which is not possible so, an error is 
# thrown
cel.temp = -300
```

**Output:**

```
The value of the tempereture is set.
The value of the temperature is:
-270

# An error is thrown
Traceback (most recent call last):
  File "main.py", line 47, in 
    cel.temp = -300
  File "main.py", line 28, in temp
    raise ValueError("It is a value error.")
ValueError: It is a value error.

```

这里，由于指定的温度值必须高于-273，因此会引发值错误。但这是-300。因此，会引发值错误。