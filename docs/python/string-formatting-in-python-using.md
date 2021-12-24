# Python 中使用%

的字符串格式

> 原文:[https://www . geesforgeks . org/string-formatting-in-python-using/](https://www.geeksforgeeks.org/string-formatting-in-python-using/)

在 Python 中，一串所需的格式可以通过不同的方法来实现。
有的是；
1)使用%
2)使用{}
3) [使用模板字符串](https://www.geeksforgeeks.org/template-class-in-python/)

本文讨论了使用%的格式。

使用%的格式类似于 C 编程语言中的“printf”。
% d–整数
% f–浮点
% s–字符串
% x–十六进制
% o–八进制

下面的例子描述了在 Python 中使用%格式化的用法

```py
# Python program to demonstrate the use of formatting using % 

# Initialize variable as a string 
variable = '15'
string = "Variable as string = %s" %(variable) 
print (string )

# Printing as raw data 
# Thanks to Himanshu Pant for this 
print ("Variable as raw data = %r" %(variable))

# Convert the variable to integer 
# And perform check other formatting options 

variable = int(variable) # Without this the below statement 
                        # will give error. 
string = "Variable as integer = %d" %(variable) 
print (string) 
print ("Variable as float = %f" %(variable)) 

# printing as any string or char after a mark 
# here i use mayank as a string 
print ("Variable as printing with special char = %cmayank" %(variable)) 

print ("Variable as hexadecimal = %x" %(variable))
print ("Variable as octal = %o" %(variable)) 
```

**输出:**

```py
Variable as string = 15
Variable as raw data = '15'
Variable as integer = 15
Variable as float = 15.000000
Variable as printing with special char = mayank
Variable as hexadecimal = f
Variable as octal = 17

```

本文由**尼克尔·库马尔·辛格(nickzuck_007)** 供稿

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论