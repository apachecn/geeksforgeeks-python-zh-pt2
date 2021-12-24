# Python 格式字符串中的%s 是什么意思？

> 原文:[https://www . geesforgeks . org/s-in-a-python-format-string/](https://www.geeksforgeeks.org/what-does-s-mean-in-a-python-format-string/)是什么意思

%符号在 Python 中用于各种数据类型和配置。%s 专门用于将字符串连接在一起。它允许我们格式化字符串中的值。它用于在字符串中包含另一个字符串。它自动提供从值到字符串的类型转换。

%s 运算符放在要指定字符串的位置。要追加到字符串中的值的数量应该等于字符串值末尾的%运算符后括号中指定的数量。

下面的 Python 代码演示了执行字符串格式化的方式。

## **简单使用%s**

## 蟒蛇 3

```py
# declaring a string variable
name = "Geek"

# append a string within a string
print("Hey, %s!" % name)
```

**输出**

```py
Hey, Geek!
```

## **多个%s**

也可以使用%s 运算符在单个字符串中追加多个字符串。字符串按照它们在括号中的位置顺序进行替换，括号中有一个%s 符号。下面的代码片段说明了这一点:

## 蟒蛇 3

```py
# declaring a string variable
var1 = "Geek!"
var2 = "Geeks for Geeks"

# append multiple strings within a string
print("Hello %s Are you enjoying being at %s for preparations." % (var1, var2))
```

**输出**

> 你好，极客！你喜欢在极客为极客做准备吗？

## **将字符串映射到%s**

但是，此运算符的出现次数必须等于%符号后要替换的字符串数。否则，将引发“类型错误:格式字符串的参数不足”类型的错误。

## 蟒蛇 3

```py
# declaring string variables
str1 = 'Understanding'
str2 = '%s'
str3 = 'at'
str4 = 'GeeksforGeeks'

# concatenating strings but %s not equal to string variables
final_str = "%s %s %s %s" % (str1, str3, str4)

# printing the final string
print("Concatenating multiple strings using Python '%s' operator:\n")
print(final_str)
```

**错误**

> 追溯(最近一次通话持续时间):
> 
> 文件"/home/c7b 65 fabd 2 ad 00163 EB 70 BBC 39685d 3 . py "，第 8 行，在
> 
> final_str = "%s %s %s %s" % (str1，str3，str4)
> 
> 类型错误:格式字符串的参数不足

**正确代码**

## 蟒蛇 3

```py
# declaring string variables
str1 = 'Understanding'
str2 = '%s'
str3 = 'at'
str4 = 'GeeksforGeeks'

# concatenating strings
final_str = "%s %s %s %s" % (str1, str2, str3, str4)

# printing the final string
print("Concatenating multiple strings using Python '%s' operator:\n")
print(final_str)
```

**输出**

```py
Concatenating multiple strings using Python '%s' operator:

Understanding %s at GeeksforGeeks
```

## **使用字典订购% s**

使用输出中的字典键，字符串以任何附加顺序打印。

## 蟒蛇 3

```py
# declaring string variables with dictionary
dct = {'str1': 'at',
       'str2': 'GeeksforGeeks',
       'str3': 'Understanding',
       'str4': '%s'}

# concatenating strings
final_str = "%(str3)s %(str4)s %(str1)s %(str2)s" % dct

# printing the final string
print("Concatenating multiple strings using Python '%s' operator:\n")
print(final_str)
```

**输出**

```py
Concatenating multiple strings using Python '%s' operator:

Understanding %s at GeeksforGeeks
```

## **列表为一个** **字符串为%s**

非字符串运算符也可以使用 Python 中的%s 符号进行格式化。元组也可以使用这个操作符插入和格式化。

## 蟒蛇 3

```py
# declaring string variables
str1 = 'Understanding'
str2 = 'integers'
str3 = 'at'
str4 = 'GeeksforGeeks = '

# declaring list variables
lst = [1, 2, 3]

# concatenating strings as well as list
final_str = "%s %s %s %s %s" % (str1, str2, str3, str4, lst)

# printing the final string
print("Concatenating multiple values using Python '%s' operator:\n")
print(final_str)
```

**输出**

```py
Concatenating multiple values using Python '%s' operator:

Understanding integers at GeeksforGeeks =  [1, 2, 3]
```