# Python 中的字符串模板类

> 原文:[https://www.geeksforgeeks.org/template-class-in-python/](https://www.geeksforgeeks.org/template-class-in-python/)

在字符串模块中，模板类允许我们为输出规范创建简化的语法。该格式使用由$构成的占位符名称和有效的 Python 标识符(字母数字字符和下划线)。占位符周围用大括号括起来，这样后面就可以有更多的字母数字字母，中间没有空格。编写$会创建一个转义的$。

### Python 字符串模板:

Python 字符串模板是通过将模板字符串传递给其构造函数来创建的。它支持基于$的替换。这个类有两个关键方法:

*   **替换(映射，**kwds):** 该方法使用字典执行替换，过程类似于基于键的映射对象。关键字参数也可以用于相同的目的。如果基于键的映射和关键字参数有相同的键，它会抛出一个 ***类型错误*** 。如果键丢失，它会返回一个 ***键错误*** 。
*   **safe _ replace(mapping，**kwds):** 该方法的行为类似于替代方法，但如果缺少某个键，它不会抛出 ***KeyError*** ，而是在结果字符串中返回一个占位符。

当字典或关键字参数中没有提供占位符时，replace()方法会引发键错误。对于邮件合并样式的应用程序，用户提供的数据可能不完整，safe _()方法可能更合适—如果数据丢失，它将保留占位符不变:

下面是几个简单的例子。
**例 1:**

## 计算机编程语言

```py
# A Simple Python template example
from string import Template

# Create a template that has placeholder for value of x
t = Template('x is $x')

# Substitute value of x in above template
print (t.substitute({'x' : 1}))
```

**输出:**

```py
x is 1
```

下面是另一个例子，我们从列表中导入学生的姓名和标记，并使用模板打印它们。
**例 2:**

## 蟒蛇 3

```py
# A Python program to demonstrate the
# working of the string template
from string import Template

# List Student stores the name and marks of three students
Student = [('Ram',90), ('Ankit',78), ('Bob',92)]

# We are creating a basic structure to print the name and
# marks of the students.
t = Template('Hi $name, you have got $marks marks')

for i in Student:
     print (t.substitute(name = i[0], marks = i[1]))
```

**输出:**

```py
Hi Ram, you have got 90 marks

Hi Ankit, you have got 78 marks

Hi Bob, you have got 92 marks
```

下面的示例显示了 safe _ 方法的实现。
**例 3:**

## 蟒蛇 3

```py
from string import Template

template = Template('$name is the $job of $company')

string = template.safe_substitute(name='Raju Kumar',
                      job='TCE')
print(string)
```

**输出:**

```py
Raju Kumar is the TCE of $company
```

请注意，我们没有向“$company”占位符提供任何数据，但它不会抛出错误，而是将占位符作为字符串返回，如上所述。

### 打印模板字符串

模板对象的“模板”属性可以用来返回模板字符串，如下所示:
**例:**

## 蟒蛇 3

```py
t = Template('I am $name from $city')
print('Template String =', t.template)
```

**输出:**

```py
Template String = I am $name from $city 
```

### 逃避$符号

**$** 可以用来逃脱 **$** 并作为弦的一部分。
**例:**

## 蟒蛇 3

```py
template = Template('$ is the symbol for $name')
string = template.substitute(name='Dollar')
print(string)
```

**输出:**

```py
$ is the symbol for Dollar 
```

### $ {标识符}

${Identifier}的工作方式类似于$Identifier。当有效的标识符字符跟在占位符后面但不是占位符的一部分时，它就派上用场了。
**例:**

## 蟒蛇 3

```py
template = Template( 'That $noun looks ${noun}y')
string = template.substitute(noun='Fish')
print(string)
```

**输出:**

```py
That Fish looks Fishy
```

模板的另一个应用是将程序逻辑从多种输出格式的细节中分离出来。这使得用自定义模板替代 XML 文件、纯文本报告和 HTML 网络报告成为可能。
请注意，还有其他方式可以打印格式化输出，如整数%d，浮点%f 等(详情请参考[本](http://geeksquiz.com/string-formatting-in-python-set-1/))
参考:[https://docs.python.org/3.3/tutorial/stdlib2.html](https://docs.python.org/3.3/tutorial/stdlib2.html)

本文由西达尔特·拉瓦尼供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论