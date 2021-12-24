# Python setattr()方法

> 原文:[https://www.geeksforgeeks.org/python-setattr-method/](https://www.geeksforgeeks.org/python-setattr-method/)

**Python setattr()方法**用于为对象属性赋值。

除了通过构造函数和对象函数将值赋给类变量的方法之外，该方法还为您提供了一种赋值的替代方法。

> **语法:** setattr(obj，var，val)
> 
> **参数:**
> 
> *   **对象:**要分配属性的对象。
> *   **var :** 必须分配的对象属性。
> *   **val :** 要分配给变量的值。
> 
> **返回:**无

### **示例 1: D** 演示 setattr 的工作原理()

## 蟒蛇 3

```
# Python code to demonstrate
# working of setattr()

# initializing class
class Gfg:
    name = 'GeeksforGeeks'

# initializing object
obj = Gfg()

# printing object before setattr
print("Before setattr name : ", obj.name)

# using setattr to change name
setattr(obj, 'name', 'Geeks4Geeks')

# printing object after setattr
print("After setattr name : ", obj.name)
```

**输出:**

```
Before setattr name : GeeksforGeeks
After setattr name : Geeks4Geeks
```

## Python setattr()属性

*   setattr()可用于将无分配给任何对象属性。
*   setattr()可用于初始化新的对象属性。

### **实施例 2: D** 说明 setattr 的特性()

## 蟒蛇 3

```
# Python code to demonstrate
# properties of setattr()

# initializing class
class Gfg:
    name = 'GeeksforGeeks'

# initializing object
obj = Gfg()

# printing object before setattr
print("Before setattr name : ", str(obj.name))

# using setattr to assign None to name
setattr(obj, 'name', None)

# using setattr to initialize new attribute
setattr(obj, 'description', 'CS portal')

# printing object after setattr
print("After setattr name : " + str(obj.name))
print("After setattr description : ", str(obj.description))
```

**输出:**

```
Before setattr name : GeeksforGeeks
After setattr name : None
After setattr description : CS portal
```

### 示例 3: Python setattr() dict

让我们以一个简单的字典“my_dict”为例，它将名称、等级和主题作为我的关键字，并将它们对应的值作为 Geeks、1223、Python。我们在这里调用一个函数 Dict2Class，它将我们的字典作为输入，并将其转换为类。然后，我们使用 setattr()函数循环遍历字典，将每个键作为属性添加到类中。

## 蟒蛇 3

```
# Turns a dictionary into a class
class Dict2Class(object):

    def __init__(self, my_dict):

        for key in my_dict:
            setattr(self, key, my_dict[key])

# Driver Code
if __name__ == "__main__":

    # Creating the dictionary
    my_dict = {"Name": "Geeks",
            "Rank": "1223",
            "Subject": "Python"}

    result = Dict2Class(my_dict)

    # printing the result
    print("After Converting Dictionary to Class : ")
    print(result.Name, result.Rank, result.Subject)
    print(type(result))
```

**输出:**

```
After Converting Dictionary to Class : 
Geeks 1223 Python
<class '__main__.Dict2Class'>
```

## Python setattr()异常

这里我们将创建对象的只读属性，如果我们试图使用 setattr()函数设置属性值，那么将出现异常。

## 蟒蛇 3

```
class Person:

    def __init__(self):
        self._name = None

    def name(self):
        print('name function called')
        return self._name

    # for read-only attribute
    n = property(name, None)

p = Person()

setattr(p, 'n', 'rajav')
```

**输出:**

```
---> 16 setattr(p, 'n', 'rajav')

AttributeError: can't set attribute
```