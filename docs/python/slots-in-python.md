# Python 中的槽

> 原文:[https://www.geeksforgeeks.org/slots-in-python/](https://www.geeksforgeeks.org/slots-in-python/)

Python 中的插槽是一种特殊的机制，用于减少对象的内存。在 Python 中，所有对象都使用动态字典来添加属性。插槽是一种静态类型方法，在这种情况下，分配属性不需要动态字典。

**语法**

```
class myClass(object):

    # defining the slots
    __slots__ = (par1, par2) 

     def __init__(self, *args, **kwargs):

         # initializing the values
         self.par1 = value1
         self.par2 = value2

```

**例 1:**

```
# defining the class.
class gfg:

    # defining the slots.
    __slots__ =('course', 'price')

    def __init__(self):

        # initializing the values
        self.course ='DSA Self Paced'
        self.price = 3999

# create an object of gfg class
a = gfg()

# print the slot
print(a.__slots__)

# print the slot variable
print(a.course, a.price)
```

**输出**

```
('course', 'price')
DSA Self Paced 3999
```

**例 2:**

```
# defining the class.
class gfg:

    # defining the slots.
    __slots__ =('course', 'price')

    def __init__(self):

        # initializing the values
        self.course ='oops'
        self.price = 5999

# create an object of gfg class
a = gfg()

# print the slot
print(a.__slots__)

# print the slot variable
print(a.course, a.price)

# change the value of the variable
a.course ='System Design'

# print the slot variable
print(a.course, a.price)

# change the value of the variable
a.price = 9999

# print the slot variable
print(a.course, a.price)
```

**输出**

```
('course', 'price')
oops 5999
System Design 5999
System Design 9999

```