# 理解 Python 数据类

> 原文:[https://www . geesforgeks . org/understanding-python-data class/](https://www.geeksforgeeks.org/understanding-python-dataclasses/)

[**【数据类】**](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/) 在 python 3.7 的最新版本中被添加为存储数据的实用工具。DataClasses 提供了一个装饰器和函数，用于自动向用户定义的类添加生成的特殊方法，如 __init__()、__repr__()和 __eq__()等。

## Python 中的数据类

**dataclass**和 Python 中的普通类一样，但是它们有一些基本的功能，比如实例化、比较和打印已经实现的类。

**安装** **数据类模块:**

```
pip install dataclasses
```

dataclass 的语法为:

> **语法:**@ dataclass . dataclass(*，init=True，repr=True，eq=True，order=False，unsafe_hash=False，frozed = False)
> 
> **参数:**
> 
> *   **init:** If True, the __init__ () method will be generated.
> *   Rep: If True, the __repr__ () method will be generated.
> *   **unsafe _ hash:** If the False __hash__ () method is generated according to the setting mode of eq and freeze
> *   **Freeze:** If true is assigned to the field, an exception will be generated.

DataClass 模块提供了一种使类不那么冗长的简便方法。让我们看看不使用数据类的传统方法。

T3】蟒 3T5

```
# creating a employee class
class employee:

    # init method or constructor
    def __init__(self, name, emp_id, age, city):

        # Instance Variable
        self.name = name
        self.emp_id = emp_id
        self.age = age
        self.city = city

    # magic function to return class object
    def __repr__(self):
        return ("employee (name={}, emp_id={}, age={}, city={} )"
                .format(self.name, self.emp_id, self.age, self.city))

    # magic function to return boolean
    def __eq__(self, check):
        return ((self.name, self.emp_id, self.age, self.city) ==
                ((check.name, check.emp_id, check.age, check.city)))

# initialization the object
emp1 = employee("Satyam", "ksatyam858", 21, 'Patna')
emp2 = employee("Anurag", "au23", 28, 'Delhi')
emp3 = employee("Satyam", "ksatyam858", 21, 'Patna')

print("employee object are :")
print(emp1)
print(emp2)
print(emp3)

# printing new line
print()

# referring two object to check equality
print("Data in emp1 and emp2 are same? ", emp1 == emp2)
print("Data in emp1 and emp3 are same? ", emp1 == emp3)
```

T6T8**输出**T1

在上面的代码中，传递参数的最大问题是 __init__、__repr_、和 __eq__。每次它都必须复制其属性并返回对象。这是处理少量数据的好方法，但假设我们要处理大量数据。这会使您的代码更加复杂。因此，这就是为什么数据类将实现使您的代码更容易和方便。

下面是同样的例子，用 Python 实现**dataclass**。

## 蟒 3

```
# A basic Data Class
# importing dataclass module
from dataclasses import dataclass

# A class for holding an employees content
@dataclass
class employee:

    # Attributes Declaration
    # using Type Hints
    name: str
    emp_id: str
    age: int
    city: str

emp1 = employee("Satyam", "ksatyam858", 21, 'Patna')
emp2 = employee("Anurag", "au23", 28, 'Delhi')
emp3 = employee("Satyam", "ksatyam858", 21, 'Patna')

print("employee object are :")
print(emp1)
print(emp2)
print(emp3)

# printing new line
print()

# referring two object to check equality
print("Data in emp1 and emp2 are same? ", emp1 == emp2)
print("Data in emp1 and emp3 are same? ", emp1 == emp3)
```