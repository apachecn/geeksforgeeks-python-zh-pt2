# 在 Python 中一起使用 enumerate()和 zip()

> 原文:[https://www . geesforgeks . org/use-enumerate-and-zip-together-in-python/](https://www.geeksforgeeks.org/use-enumerate-and-zip-together-in-python/)

在本文中，我们将讨论如何在 python 中使用 enumerate()和 zip()函数。

Python [enumerate()](https://www.geeksforgeeks.org/enumerate-in-python/) 用于使用 list()方法转换成元组列表。

> **语法:**
> 
> 枚举(可迭代，开始=0)
> 
> **参数**:
> 
> *   Iterable:任何支持迭代的对象
> *   开始:启动计数器的索引值，默认为 0

Python [zip()](https://www.geeksforgeeks.org/zip-in-python/) 方法接受 iterable 或 containers，并返回一个迭代器对象，该对象已经映射了所有容器的值。

**语法:**

```py
zip(*iterators) 
```

使用两者，我们可以通过一次使用枚举和压缩函数来迭代两个或多个列表/对象。

**语法**:

```py
enumerate(zip(list1,list2,.,list n))
```

我们可以在 for 循环中迭代这个。

**语法:**

```py
for var1,var2,.,var n in enumerate(zip(list1,list2,..,list n))
```

哪里，

*   列表 1、列表 2、。是输入列表
*   var1、var2、…是迭代列表的迭代器

**示例:**在 Python 中一起使用 enumerate()和 zip()

## py S3

```py
# create a list of names
names = ['sravan', 'bobby', 'ojaswi', 'rohith', 'gnanesh']

# create a list of subjects
subjects = ['java', 'python', 'R', 'cpp', 'bigdata']

# create a list of marks
marks = [78, 100, 97, 89, 80]

# use enumerate() and zip() function
# to iterate the lists
for i, (names, subjects, marks) in enumerate(zip(names, subjects, marks)):
    print(i, names, subjects, marks)
```

**输出**:

```py
0 sravan java 78
1 bobby python 100
2 ojaswi R 97
3 rohith cpp 89
4 gnanesh bigdata 80
```

我们也可以通过使用 tuple(t)来做到这一点

**语法:**

```py
for i, t in enumerate(zip(names, subjects,marks))
```

它以元组格式返回数据

**示例**:在 Python 中一起使用 enumerate()和 zip()

## 蟒蛇 3

```py
# create a list of names
names = ['sravan', 'bobby', 'ojaswi', 'rohith', 'gnanesh']

# create a list of subjects
subjects = ['java', 'python', 'R', 'cpp', 'bigdata']

# create a list of marks
marks = [78, 100, 97, 89, 80]

# use enumerate() and zip() function
# to iterate the lists with t function
for i, t in enumerate(zip(names, subjects, marks)):
    print(i, t)
```

**输出:**

```py
0 ('sravan', 'java', 78)
1 ('bobby', 'python', 100)
2 ('ojaswi', 'R', 97)
3 ('rohith', 'cpp', 89)
4 ('gnanesh', 'bigdata', 80)
```

我们也可以在上面的方法中使用 t[index]来获得输出

**示例**:在 Python 中一起使用 enumerate()和 zip()

## 蟒蛇 3

```py
# create a list of names
names = ['sravan', 'bobby', 'ojaswi', 'rohith', 'gnanesh']

# create a list of subjects
subjects = ['java', 'python', 'R', 'cpp', 'bigdata']

# create a list of marks
marks = [78, 100, 97, 89, 80]

# use enumerate() and zip() function
# to iterate the lists with t function
for i, t in enumerate(zip(names, subjects, marks)):
    print(i, t[0], t[1], t[2])
```

**输出:**

```py
0 sravan java 78
1 bobby python 100
2 ojaswi R 97
3 rohith cpp 89
4 gnanesh bigdata 80
```