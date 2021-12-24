# Python 中的 vars()函数

> 原文:[https://www.geeksforgeeks.org/vars-function-python/](https://www.geeksforgeeks.org/vars-function-python/)

这是 Python 中的一个内置函数。vars()方法只接受一个参数，这个参数也是可选的。它将一个对象作为参数，该参数可以是模块、类、实例或任何具有 __dict__ 属性的对象。
**语法:**

```py
vars(object)
```

如果模块、类、实例或任何其他对象具有 __dict__ 属性，则方法返回该对象的 __dict__ 属性。**如果对象与属性不匹配，将引发类型错误异常**。模块和实例等对象具有可更新的 __dict__ 属性，但是，其他对象可能对其 __dict__ 属性有书面限制。**当传递空参数**时，vars()的作用类似于 locals()方法，这意味着 locals 字典只对读取有用，因为对 locals 字典的更新被忽略。

```py
# Python program to illustrate
# working of vars() method in Python

class Geeks:
  def __init__(self, name1 = "Arun", num2 = 46, name3 = "Rishab"):
    self.name1 = name1
    self.num2 = num2
    self.name3 = name3

GeeksforGeeks = Geeks()
print(vars(GeeksforGeeks))
```

输出:

```py
{'num2': 46, 'name1': 'Arun', 'name3': 'Rishab'}
```

```py
# Python program to illustrating 
# the use of vars() and locals
# when no argument is passed and 
# how vars() act as locals().
class Geeks(object):
    def __init__(self):
        self.num1 = 20
        self.num2 = "this is returned"

    def __repr__(self):
        return "Geeks() is returned"

    def loc(self):
        ans = 21
        return locals()

    # Works same as locals()
    def code(self):
        ans = 10
        return vars()

    def prog(self):
        ans = "this is not printed"
        return vars(self)

if __name__ == "__main__":
    obj = Geeks()
    print (obj.loc())
    print (obj.code())
    print (obj.prog())
```

输出:

```py
{'ans': 21, 'self': Geeks() is returned}
{'ans': 10, 'self': Geeks() is returned}
{'num1': 20, 'num2': 'this is returned'}

```