# Python–星号或星号运算符(* )

> 原文:[https://www . geesforgeks . org/python-star-or-asterisk-operator/](https://www.geeksforgeeks.org/python-star-or-asterisk-operator/)

Python 中有很多地方会用到*和*。许多 Python 程序员，即使是中级程序员，在遇到 Python 中的星号(*)字符时也经常感到困惑。

学习完这篇文章，你会对 Python 中的星号(*)运算符有一个坚实的理解，并在这个过程中成为一个更好的编码者！

### **下面是 Python 中星号(*)运算符的各种用法:**

*   **乘法:**
    在乘法中，我们使用星号/星形运算符作为中缀运算符来相乘两个数字。

## 蟒蛇 3

```py
# using asterisk
mul = 5 * 7
print (mul)
```

**输出:**

```py
35
```

*   **求幂:**
    使用两个(**) Start 运算符我们可以得到任意整数值的指数值。

## 蟒蛇 3

```py
a = 5
b = 3

# using asterisk
result = a ** b
print(result)
```

**输出:**

```py
125
```

*   **列表的乘法:**
    借助“*”我们可以将列表的元素相乘，它将代码转换成单行。

## 蟒蛇 3

```py
# using asterisk
list = ['geeks '] * 3

print(list)
```

**输出:**

```py
['geeks ', 'geeks ', 'geeks ']
```

*   **使用位置参数解包函数。**
    这种方法在以原始格式(没有任何逗号和括号)打印数据时非常有用。许多程序员试图通过函数的卷积来去掉逗号和括号，因此这个简单的前缀星号可以解决你在解包它们时的问题。

## 蟒蛇 3

```py
arr = ['sunday', 'monday', 'tuesday', 'wednesday']

# without using asterisk
print(' '.join(map(str,arr))) 

# using asterisk
print (*arr)
```

**输出:**

```py
sunday monday tuesday wednesday
sunday monday tuesday wednesday
```

*   **传递函数使用任意数量的位置参数**
    这里单星号(*)也用于**参数*。它用于向函数传递可变数量的参数，它主要用于传递非键参数和可变长度的参数列表。
    它有很多用途，下面举例说明了这样一个例子，我们做了一个加法函数，它接受任意数量的参数，并且能够使用 **args* 将它们加在一起。

## 蟒蛇 3

```py
# using asterisk
def addition(*args):
  return sum(args)

print(addition(5, 10, 20, 6))
```

**输出:**

```py
41
```

*   **传递函数使用任意数量的位置参数**
    这里双星号(**)也用作 ***kwargs* ，双星号允许传递关键字参数。这个特殊的符号用于传递关键字参数和可变长度参数列表。它有许多用途，下面举例说明

## 蟒蛇 3

```py
# using asterisk
def food(**kwargs):
  for items in kwargs:
    print(f"{kwargs[items]} is a {items}")

food(fruit = 'cherry', vegetable = 'potato', boy = 'srikrishna')
```

**输出:**

```py
cherry is a fruit
potato is a vegetable
srikrishna is a boy
```

只是另一个使用 ***kwargs* 的例子，为了更好的理解。

## 蟒蛇 3

```py
# using asterisk
def food(**kwargs):
  for items in kwargs:
    print(f"{kwargs[items]} is a {items}")

dict = {'fruit' : 'cherry', 'vegetable' : 'potato', 'boy' : 'srikrishna'}
# using asterisk
food(**dict)
```

**输出:**

```py
cherry is a fruit
potato is a vegetable
srikrishna is a boy
```