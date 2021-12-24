# Python 中的字符串格式

> 原文:[https://www.geeksforgeeks.org/string-formatting-in-python/](https://www.geeksforgeeks.org/string-formatting-in-python/)

在本文中，我们将讨论如何格式化字符串 Python。字符串格式化是在字符串中动态注入内容并呈现字符串的过程。有四种不同的方式来执行字符串格式化:-

*   Format with% Operator.
*   Format with format () string method.
*   Format with string literal, called F string.
*   Format with string template class

因此，我们将看到上述方法的全部，我们还将关注哪种字符串格式策略是最好的。

## 使用%运算符格式化字符串

这是最古老的字符串格式化方法。这里我们使用模 [**%** 运算符](https://www.geeksforgeeks.org/string-formatting-in-python-using/)。模 **%** 也被称为“字符串格式运算符”。

**示例:使用%运算符**

## 对字符串进行格式化

```
print("The mangy, scrawny stray dog %s gobbled down" +
      "the grain-free, organic dog food." %'hurriedly')
```

**输出:**

> 这只又脏又瘦的流浪狗赶紧狼吞虎咽地吃下了这种不含谷物的有机狗粮。

您也可以一次注入多个字符串，还可以使用变量在字符串中插入对象。

**示例:使用%运算符**

## 注入多个字符串【python 3】

```
x = 'looked'

print("Misha %s and %s around"%('walked',x))
```

**输出:**

```
Misha walked and looked around.
```

**'%s'** 类似地用于注入字符串 **'%d'** 用于整数， **'%f'** 用于浮点值， **'%b'** 用于二进制格式。对于所有格式，转换方法请访问官方文档。

**示例:**

## 蟒蛇 3

```
print('Joe stood up and %s to the crowd.' %'spoke')

print('There are %d dogs.' %4)
```

**输出:**

```
Joe stood up and spoke to the crowd.
There are 4 dogs.
```

### **使用占位符方法浮动精度:**

浮点数使用格式 **%a.bf** 。这里， **a** 将是字符串中出现的最小位数；如果整个数字没有这么多数字，这些可能会用空格填充。接近于此， **bf** 代表小数点后要显示多少位。

让我们看几个例子:

**示例 1:浮点精度使用%运算符**

## python 3

```
print('The value of pi is: %5.4f' %(3.141592))
```

**输出:**

```
The value of pi is: 3.1416
```

**例 2:**

## 蟒 3

```
print('Floating point numbers: %1.0f' %(13.144))
```

**输出:**

```
Floating point numbers: 13
```

**示例 3:可以在单个打印语句中使用多种格式转换类型**

## python 3

```
variable = 12

string = "Variable as integer = %d \n\
Variable as float = %f" %(variable, variable)

print (string)
```

**输出**

```
Variable as integer = 12 
Variable as float = 12.000000
```

**注意:**要了解更多关于%-格式的信息，请参考 Python 中使用% 的[字符串格式](https://www.geeksforgeeks.org/string-formatting-in-python-using/)

## 使用 format()方法格式化字符串

[Format()方法](https://www.geeksforgeeks.org/python-string-format-method/)是 Python3 为了更有效地处理复杂的字符串格式而引入的。格式化程序通过将一对花括号{ }定义的一个或多个替换字段和占位符放入字符串并调用 str.format()来工作。我们希望放入占位符并与作为参数传递到 format 函数的字符串连接的值。

> **句法:**“此处串{}则也{}”。格式(‘某物 1’，‘某物 2’)

**示例:使用 format()方法格式化字符串**

## python 3

```
print('We all are {}.'.format('equal'))
```

**输出:**

```
We all are equal.
```

**。format()** 方法相比占位符方法有很多优势:

*   We can insert objects by using index-based locations:

## python 3

```
print('{2} {1} {0}'.format('directions',
                           'the', 'Read'))
```

**输出:**

```
Read the directions.
```

*   We can insert objects by using the specified keywords:

## python 3

```
print('a: {a}, b: {b}, c: {c}'.format(a = 1,
                                      b = 'Two',
                                      c = 12.3))
```

**输出:**

```
a: 1, b: Two, c: 12.3
```

*   We can reuse inserted objects to avoid duplication:

## python 3

```
print('The first {p} was alright, but the {p} {p} was tough.'.format(p = 'second'))
```

**输出:**

> 第一秒还可以，但第二秒很难熬。

**用. format()方法浮动精度:**

> **语法:**{[索引]:[宽度][。精度][类型]}

该类型可以与格式代码一起使用:

*   **[d]** represents an integer.
*   **[f]** represents a floating-point number.
*   **[b]** represents a binary number.
*   **[o]** represents an octal number.
*   **[x]** represents an octal hexadecimal number.
*   **[s]** denotes a character string.

**例:**

## 蟒 3

```
print('The valueof pi is: %1.5f' %3.141592)

# vs.

print('The valueof pi is: {0:1.5f}'.format(3.141592))
```

**输出:**

```
The valueof pi is: 3.14159
The valueof pi is: 3.14159
```

**注意:**要了解更多 str.format()，请参考 Python 中的 [format()函数](https://www.geeksforgeeks.org/python-format-function/)

## 使用格式字符串的格式化字符串

PEP 498 引入了一种新的字符串格式化机制，称为文字字符串插值或更常见的 [F 字符串](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/)(因为在字符串文字前面有一个前导 F 字符)。f-strings 背后的思想是使字符串插值更简单。

要创建 f 字符串，请在字符串前面加上字母“f”。字符串本身的格式可以与 str.format()的格式非常相似。F-strings 提供了一种简洁方便的方法，可以将 python 表达式嵌入到字符串文字中进行格式化。

**示例:用 F 字符串格式化字符串**

## python 3

```
name = 'Ele'

print(f"My name is {name}.")
```

**输出:**

```
My name is Ele.
```

这种新的格式语法非常强大和简单。您还可以插入任意 Python 表达式，甚至可以在其中进行算术运算。

**示例:使用 F 字符串的算术运算**

## python 3

```
a = 5

b = 10

print(f"He said his age is {2 * (a + b)}.")
```

**输出:**

```
He said his age is 30.
```

我们也可以在 **f-string** 格式中使用**λ**表达式。

**示例:使用 F 字符串的λ表达式**

## python 3

```
print(f"He said his age is {(lambda x: x*2)(3)}")
```

**输出:**

```
He said his age is 6
```

**f-String 方法中的浮点精度:**

> **语法:** {value:{width}。{precision}}

**示例:浮动精度使用 F 字符串**

## python 3

```
num = 3.14159

print(f"The valueof pi is: {num:{1}.{5}}")
```

**输出:**

```
The valueof pi is: 3.1416
```

**注意:**要了解更多 f 弦，请参考 Python 中的 [f 弦](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/)

## 字符串模板类

在字符串模块中，模板类允许我们为输出规范创建简化的语法。该格式使用由$构成的占位符名称和有效的 Python 标识符(字母数字字符和下划线)。占位符周围用大括号括起来，这样后面就可以有更多的字母数字字母，中间没有空格。编写$会创建一个转义的$:

**示例:使用模板类**

## python 3

```
# Python program to demonstrate
# string interpolation

from string import Template

n1 = 'Hello'
n2 = 'GeeksforGeeks'

# made a template which we used to
# pass two variable so n3 and n4
# formal and n1 and n2 actual
n = Template('$n3 ! This is $n4.')

# and pass the parameters into the
# template string.
print(n.substitute(n3=n1, n4=n2))
```

格式化字符串

**注意:**要了解更多字符串模板类，请参考 Python 中的[字符串模板类](https://www.geeksforgeeks.org/template-class-in-python/)

## 哪种字符串格式化方法最好？

**f-strings** 比**%-formating**和 **str.format()** 都要更快更好。f-string 表达式是在运行时计算的，我们也可以在 f-string 中嵌入表达式，使用非常简单的语法。大括号内的表达式在运行时进行计算，然后与 f 字符串的字符串部分放在一起，然后返回最终的字符串。

**注意:**如果在 Python 3.6+上使用 f-Strings，如果不在 Python 3.6+上使用. format()方法。