# Python 函数为什么以及如何变得容易？

> 原文:[https://www . geesforgeks . org/why-and-how-is-python-functions-has hable/](https://www.geeksforgeeks.org/why-and-how-are-python-functions-hashable/)

所以从一个问题开始，即为什么 Python 函数是可散列的以及如何散列的？首先，人们应该知道 hashable 在 Python 中的实际含义。因此，hashable 是 Python 对象的一个特性，它告诉对象是否有哈希值。如果对象有一个哈希值，那么它可以用作字典的关键字或集合中的元素。

如果一个对象的哈希值在其整个生命周期内不变，则该对象是可哈希的。Python 有一个内置的哈希方法(__hash__())，可以与其他对象进行比较。为了进行比较，需要 __eq__()或 __cmp__()方法，如果 hashable 对象相等，则它们具有相同的哈希值。Python 中所有不可变的内置对象都像元组一样是可散列的，而像列表和字典这样的可变容器是不可散列的。

默认情况下，作为用户定义类的实例的对象是可散列的，它们都比较不相等，它们的散列值是它们的 id()。

**例:**考虑两个取值相同的元组 T1、t2，看看区别:

## 蟒蛇 3

```py
t1 = (1, 5, 6)

t2 = (1, 5, 6)

# show the id of object
print(id(t1))

print(id(t2))
```

**输出:**

```py
140040984150664
140040984150880

```

在上面的例子中，两个对象是不同的，对于不可变类型，哈希值取决于存储的数据，而不是它们的 id。

**示例:**让我们看看 lambda 函数是否可散列。

## 蟒蛇 3

```py
# create a one-line function
l = lambda x : 1

# show the hash value
print(hash(l))

# show the id value
print(id(l))

# show the hash value
print (l.__hash__())
```

**输出:**

```py
-9223363246992694337
140637793303544
-9223363246992694337

```

因此，lambda 函数是可散列的。

**示例:**让我们看看用户定义的基于 def 的函数是否可散列。

## 蟒蛇 3

```py
# create an empty function
def fun():
  pass

# print types of function
print(type(fun))

# print hash value
print(fun.__hash__())

# print hash value
print(hash(fun))
```

**输出:**

```py
<class 'function'>
-9223363242199589441
-9223363242199589441 

```

因此，任何用户定义的函数都是可散列的，因为它的散列值在其生存期内保持不变。