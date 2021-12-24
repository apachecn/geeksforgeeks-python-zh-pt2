# Python 字符串串联

> 原文:[https://www.geeksforgeeks.org/python-string-concatenation/](https://www.geeksforgeeks.org/python-string-concatenation/)

在 Python 中，[字符串](https://www.geeksforgeeks.org/python-strings/)是表示 Unicode 字符的字节数组。但是，Python 没有字符数据类型，单个字符只是长度为 1 的字符串。方括号[]可用于访问字符串的元素。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# strings

# Assign Welcome string to the variable var1
var1 = "Welcome"

# Assign statistics string to the variable var2
var2 = "statistics"

# print the result
print(var1)
print(var2)
```

**Output**

```
Welcome
statistics
```

## Python 中的字符串连接

字符串串联是**组合两个字符串**的技术。字符串连接可以通过多种方式完成。
**我们可以使用以下方式执行字符串连接:**

1.  [使用+运算符](#+)

2.  [使用 join()方法](#join)T2】
3.  [使用%运算符](#%)

4.  [使用格式()功能](#format)

5.  使用，(逗号)

#### 使用+运算符

使用+运算符进行字符串连接非常容易。该运算符可用于将多个字符串相加。但是，参数必须是字符串。
**注意:**字符串是不可变的，因此，每当它被连接时，它就被分配给一个新的变量。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# string concatenation

# Defining strings
var1 = "Hello "
var2 = "World"

# + Operator is used to combine strings
var3 = var1 + var2
print(var3)
```

**Output**

```
Hello World
```

这里，变量 var1 存储字符串“Hello”，变量 var2 存储字符串“World”。+运算符组合存储在 var1 和 var2 中的字符串，并存储在另一个变量 var3 中。

#### 使用连接()方法

[join()](https://www.geeksforgeeks.org/join-function-python/) 方法是一个字符串方法，返回一个字符串，其中序列的元素通过字符串分隔符连接在一起。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# string concatenation

var1 = "Hello"
var2 = "World"

# join() method is used to combine the strings
print("".join([var1, var2]))

# join() method is used here to combine
# the string with a separator Space(" ")
var3 = " ".join([var1, var2])

print(var3)
```

**Output**

```
HelloWorld
Hello World
```

在上面的例子中，变量 var1 存储字符串“Hello”，变量 var2 存储字符串“World”。join()方法组合了存储在 var1 和 var2 中的字符串。join 方法只接受列表，因为它的参数和列表大小可以是任何值。我们可以将组合后的字符串存储在另一个变量 var3 中，该变量由空格分隔。
**注:**了解更多加入()方法[点击此处](https://www.geeksforgeeks.org/join-function-python/)。

#### 使用%运算符

我们可以使用%运算符进行字符串格式化，它也可以用于字符串连接。当我们想要连接字符串并执行简单的格式化时，它非常有用。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# string concatenation

var1 = "Hello"
var2 = "World"

# % Operator is used here to combine the string
print("% s % s" % (var1, var2))
```

**Output**

```
Hello World
```

这里，运算符%将存储在变量 1 和变量 2 中的字符串组合在一起。%s 表示字符串数据类型。两个变量中的值都被传递给字符串%s，并变成“Hello World”。

#### 使用 format()函数

[str.format()](https://www.geeksforgeeks.org/python-format-function/) 是 Python 中的字符串格式化方法之一，允许多次替换和值格式化。这个方法允许我们通过位置格式化来连接字符串中的元素。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# string concatenation

var1 = "Hello"
var2 = "World"

# format function is used here to
# combine the string
print("{} {}".format(var1, var2))

# store the result in another variable
var3 = "{} {}".format(var1, var2)

print(var3)
```

**Output**

```
Hello World
Hello World
```

这里，format()函数组合了存储在 var1 和 var2 中的字符串，并存储在另一个变量 var3 中。大括号{}用于设置字符串的位置。第一个变量存储在第一个大括号中，第二个变量存储在第二个大括号中。最后打印值“你好世界”。
**注:**了解更多格式()功能[点击此处](https://www.geeksforgeeks.org/python-format-function/)。

#### 使用，(逗号)

“，”是使用“+”进行字符串连接的很好的替代方法。当你想包含一个空格时。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# string concatenation

var1 = "Hello"
var2 = "World"

# , to combine data types with a single whitespace.
print(var1, var2)
```

**Output**

```
Hello World
```

当您想要组合数据类型时，请使用。