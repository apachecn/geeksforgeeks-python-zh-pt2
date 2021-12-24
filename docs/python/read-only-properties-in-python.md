# Python 中的只读属性

> 原文:[https://www . geesforgeks . org/只读-python 中的属性/](https://www.geeksforgeeks.org/read-only-properties-in-python/)

**先决条件:** [Python 类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)

类是用户定义的蓝图或原型，从中创建对象。类提供了一种将数据和功能捆绑在一起的方法。创建一个新类会创建一个新类型的对象，从而允许创建该类型的新实例。简单来说，我们假设一个班级**学生**，一个学生可以有很多属性，比如姓名、课程、学生证等。现在让我们假设我们有一个叫安妮塔的学生在攻读工商管理硕士学位，安妮塔是学生课的对象。

**示例:**

```
class student:

    def __init__(self, name, course):
        self.name = name
        self.course = course

    def studentid(self):
        return "student's identification number is \
        {}{}".format(self.name, self.course)

student1 = student("Anita", "MBA")
print(student1.studentid())
```

**输出:**

```
student's identification number is AnitaMBA
```

现在，我们希望将学生证作为一种属性而不是方法来访问。为此所需要的只是在方法之前添加 **[@property](https://www.geeksforgeeks.org/python-property-decorator-property/)** 装饰器。

**示例:**

```
class student:

    def __init__(self, name, course):
        self.name = name
        self.course = course

    @property
    def studentid(self):
        return "student's identification number is \
        {}{}".format(self.name, self.course)

student1 = student("Anita", "MBA")
print(student1.studentid)
```

**输出:**

```
student's identification number is AnitaMBA
```

只读属性是没有设置器的属性装饰器。这里的学生证是只读属性，因为它没有设置器。一般来说，它意味着价值是不可改变的。为了理解，让我们再举一个例子:

**示例:**

```
class employee:
    def __init__(self, basesalary, yearsofworking):
        self.basesalary = basesalary
        self.yearsofworking = yearsofworking

    @property
    def salary(self):
        self.salary = 50000

amit = employee(20000, 5)
amit.salary = 10000
print(amit.basesalary, amit.yearsworking, amit.salary)
```

**输出:**

> 回溯(最近一次调用最后一次):
> 文件/home/e 029 e0b 9 ccad 85905 e 22 DD 5a 91943897 . py】，第 14 行，在<module>中
> amit.salary = 10000
> 属性错误:无法设置属性</module>

要解决这个问题，需要在代码中添加一个 setter。执行此操作后，它将不再是只读属性。

**示例:**

```
class employee:
    def __init__(self, basesalary, yearsofworking):
        self.basesalary = basesalary
        self.yearsofworking = yearsofworking
        self._salary = 0

    @property
    def salary(self):
        return self._salary

    @salary.setter
    def salary(self, salary):
        self._salary = salary

amit = employee(20000, 5)
amit.salary = 10000
print(amit.basesalary, amit.yearsofworking, amit.salary)
```

**输出:**

```
20000 5 10000
```