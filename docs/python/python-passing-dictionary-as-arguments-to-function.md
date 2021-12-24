# Python:将字典作为参数传递给函数

> 原文:[https://www . geesforgeks . org/python-passing-dictionary-as-arguments-to-function/](https://www.geeksforgeeks.org/python-passing-dictionary-as-arguments-to-function/)

Python 中的字典是无序且可变的数据集合。与列表使用的数字索引不同，字典使用键作为特定值的索引。它可用于存储不相关的数据类型，但作为现实实体相关的数据。密钥本身用于使用特定的值。

> **参考下面的文章，获得关于 Python 字典的想法。**
> 
> *   [Python 词典](https://www.geeksforgeeks.org/python-dictionary/)

#### 将字典作为参数传递

在 Python 中，一切都是一个对象，所以字典可以作为参数传递给函数，就像传递其他变量一样。

**示例:**

```py
# Python program to demonstrate
# passing dictionary as argument

# A function that takes dictionary
# as an argument
def func(d):

    for key in d:
        print("key:", key, "Value:", d[key])

# Driver's code
D = {'a':1, 'b':2, 'c':3}
func(D)
```

**输出:**

```py
key: b Value: 2
key: a Value: 1
key: c Value: 3

```

**作为夸脱通过字典**

“`kwargs`”代表关键词参数。它用于将高级数据对象(如字典)传递给函数，因为在这样的函数中，人们不知道参数的数量，因此通过在传递类型中添加“**”来正确处理传递的数据。

**例 1:**

```py
# Python program to demonstrate
# passing dictionary as kwargs

def display(**name):

    print (name["fname"]+" "+name["mname"]+" "+name["lname"])

def main():

    # passing dictionary key-value 
    # pair as arguments
    display(fname ="John",
            mname ="F.", 
            lname ="Kennedy")
# Driver's code
main()
```

**输出:**

```py
John F. Kennedy

```

**例 2:**

```py
# Python program to demonstrate
# passing dictionary as kwargs

def display(x = 0, y = 0, **name):

    print (name["fname"]+" "+name["mname"]+" "+name["lname"])
    print ("x =", x)
    print ("y =", y)

def main():
    # passing dictionary key-value 
    # pair with other arguments
    display(2, fname ="John", mname ="F.", lname ="Kennedy")

# Driver's code
main()
```

**输出:**

```py
John F. Kennedy
x = 2
y = 0

```