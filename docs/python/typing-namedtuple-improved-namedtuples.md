# 打字。命名套件–改进的命名套件

> 原文:[https://www . geesforgeks . org/typing-named tuple-improved-named tuples/](https://www.geeksforgeeks.org/typing-namedtuple-improved-namedtuples/)

Python 3.6 中添加的**打字**模块的**命名类**是**集合**模块中命名类的弟弟。主要区别是定义新记录类型的更新语法和对类型提示的支持。像字典一样，命名元组包含散列到特定值的键。但是在相反，它支持从键值访问和迭代，这是字典所缺乏的功能。

### **创建一个名称对**

名称可以使用以下语法来创建:

```
class class_name(NamedTuple):
    field1: datatype
    field2: datatype
```

这相当于:

```
class_name = collections.namedtuple('class_name', ['field1', 'field2'])
```

**例:**

## 蟒蛇 3

```
# importing the module
from typing import NamedTuple

# creating a class
class Website(NamedTuple):
    name: str
    url: str
    rating: int

# creating a NamedTuple
website1 = Website('GeeksforGeeks',
                   'geeksforgeeks.org',
                   5)

# displaying the NamedTuple
print(website1)
```

**输出:**

```
Website(name='GeeksforGeeks', url='geeksforgeeks.org', rating=5)
```

### 访问操作

1.  **按索引访问:**namedtuple()的属性值是有序的，可以使用索引号进行访问，不像字典那样不能通过索引进行访问。
2.  **通过键名访问:**与字典中一样，也允许通过键名访问。
3.  **使用 getattr():** 这是另一种访问值的方法，方法是将 namedtuple 和 key-value 作为参数。

**例:**

## 蟒蛇 3

```
# importing the module
from typing import NamedTuple

# creating a class
class Website(NamedTuple):
    name: str
    url: str
    rating: int

# creating a NamedTuple
website1 = Website('GeeksforGeeks',
                   'geeksforgeeks.org',
                   5)

# accessing using index
print("The name of the website is : ", end = "")
print(website1[0])

# accessing using name
print("The URL of the website is : ", end = "")
print(website1.url)

# accessing using getattr() 
print("The rating of the website is : ", end = "")
print(getattr(website1, 'rating'))
```

**输出:**

```
The name of the website is : GeeksforGeeks
The URL of the website is : geeksforgeeks.org
The rating of the website is : 5
```

这些字段是不可变的。因此，如果我们尝试更改这些值，我们会得到属性错误:

## 蟒蛇 3

```
# importing the module
from typing import NamedTuple

# creating a class
class Website(NamedTuple):
    name: str
    url: str
    rating: int

# creating a NamedTuple
website1 = Website('GeeksforGeeks',
                   'geeksforgeeks.org',
                   5)

# changing the attribute value
website1.name = "Google"
```

**输出:**

```
AttributeError: can't set attribute

```