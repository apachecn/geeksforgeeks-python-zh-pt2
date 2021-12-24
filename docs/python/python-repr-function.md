# Python repr()函数

> 原文:[https://www.geeksforgeeks.org/python-repr-function/](https://www.geeksforgeeks.org/python-repr-function/)

**Python repr()函数**返回传递给它的对象的可打印表示。

**语法:**

```py
repr(object)
```

**参数:**

```py
object : The object whose printable representation is to be returned.
```

**返回值:**

```py
Returns a string.
```

可以在类中定义 __repr__()方法来控制该函数为其对象返回什么。

### **示例 1:** 将字符串对象传递给 repr 方法

## 蟒蛇 3

```py
strObj = 'geeksforgeeks'

print(repr(strObj))
```

**Output**

```py
'geeksforgeeks'
```

### **示例 2:** 将 set 对象传递给 repr 方法

## 蟒蛇 3

```py
num = {1, 2, 3, 4, 5}

# printable representation of the set
printable_num = repr(num)
print(printable_num)
```

**Output**

```py
{1, 2, 3, 4, 5}
```

### **示例 3:** 在类中定义 __repr__()方法

## 蟒蛇 3

```py
class geek:
    def __init__(self, name):
        self.name = name

    # defining __repr__() method to control what
    # to return for objects of geek
    def __repr__(self):
        return self.name

geek1 = geek('mohan')
print(repr(geek1))
```

**Output**

```py
mohan
```

**说明:**

repr()在类中定义，特殊方法返回对象的名称属性，geek 类的对象被创建，字符串被传递给它，字符串的可打印表示被打印。