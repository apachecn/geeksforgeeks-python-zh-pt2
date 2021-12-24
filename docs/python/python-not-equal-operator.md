# Python 不等运算符

> 原文:[https://www.geeksforgeeks.org/python-not-equal-operator/](https://www.geeksforgeeks.org/python-not-equal-operator/)

在这篇文章中，我们将看到！=(不相等)运算符。在 Python 中**！=** 定义为**不等于**运算符。如果两边的操作数不相等，则返回**真**，如果相等，则返回**假**。

**注意:**请务必记住，如果值相同但数据类型不同，此比较运算符将返回 True。

> **语法:**值 A！=值 B

### **示例 1:** 比较相同数据类型的不同值

## 蟒蛇 3

```
A = 1
B = 2
C = 2

print(A!=B)
print(B!=C)
```

**输出:**

```
True
False
```

### **示例 2:** 比较不同数据类型的相同值

## 蟒蛇 3

```
A = 1
B = 1.0
C = "1"

print(A!=B)
print(B!=C)
print(A!=C)
```

**输出:**

```
False
True
True
```

### 示例 3: Python 不等于自定义对象

每当使用不等运算符时，就会调用 **__ne__()** 。我们可以覆盖这个函数来改变不等运算符的性质。

## 蟒蛇 3

```
class Student:

    def __init__(self, name):
        self.student_name = name

    def __ne__(self, x):
        # return true for different types
        # of object
        if type(x) != type(self):
            return True

        # return True for different values
        if self.student_name != x.student_name:
            return True
        else:
            return False

s1 = Student("Shyam")
s2 = Student("Raju")
s3 = Student("babu rao")

print(s1 != s2)
print(s2 != s3)
```

**输出:**

```
True
True
```