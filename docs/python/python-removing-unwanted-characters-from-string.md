# Python |删除字符串中不需要的字符

> 原文:[https://www . geesforgeks . org/python-从字符串中删除不需要的字符/](https://www.geeksforgeeks.org/python-removing-unwanted-characters-from-string/)

程序员面临的一般问题是从整个字符串中删除一个字符。但有时要求远远超过，并要求删除超过 1 个字符，但这种恶意字符的清单。这些字符可以是特殊字符的形式，用于重建有效密码和许多其他可能的应用。让我们讨论执行这个特殊任务的某些方法。
**方法#1:使用 replace()**
可以在循环中使用 replace()检查一个坏字符，然后用空字符串替换它，从而删除它。这是最基本的方法，从性能的角度来看效率很低。

## 蟒蛇 3

```
# Python3 code to demonstrate
# removal of bad_chars
# using replace()

# initializing bad_chars_list
bad_chars = [';', ':', '!', "*"]

# initializing test string
test_string = "Ge;ek * s:fo ! r;Ge * e*k:s !"

# printing original string
print ("Original String : " + test_string)

# using replace() to
# remove bad_chars
for i in bad_chars :
    test_string = test_string.replace(i, '')

# printing resultant string
print ("Resultant list is : " + str(test_string))
```

**输出:**

```
Original String : Ge;ek*s:fo!r;Ge*e*k:s!
Resultant list is : GeeksforGeeks

```

**方法 2:使用 join() +生成器**
通过使用 join()我们重新制作字符串。在生成器函数中，我们指定逻辑来忽略坏字符中的字符，从而构造没有坏字符的新字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate
# removal of bad_chars
# using join() + generator

# initializing bad_chars_list
bad_chars = [';', ':', '!', "*"]

# initializing test string
test_string = "Ge;ek * s:fo ! r;Ge * e*k:s !"

# printing original string
print ("Original String : " + test_string)

# using join() + generator to
# remove bad_chars
test_string = ''.join(i for i in test_string if not i in bad_chars)

# printing resultant string
print ("Resultant list is : " + str(test_string))
```

**输出:**

```
Original String : Ge;ek*s:fo!r;Ge*e*k:s!
Resultant list is : GeeksforGeeks

```

**方法#3:使用 translate()**
执行这个特定任务最优雅的方式，这个方法基本上是用来实现这类问题本身的解决方案，我们可以将每个 bad_char 翻译成空字符串并得到过滤后的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate
# removal of bad_chars
# using translate()
import string
# initializing bad_chars_list
bad_chars = [';', ':', '!', "*"]

# initializing test string
test_string = "Ge;ek * s:fo ! r;Ge * e*k:s !"

# printing original string
print ("Original String : " + test_string)

# using translate() to
# remove bad_chars
delete_dict = {sp_character: '' for sp_character in string.punctuation}
delete_dict[' '] = ''
table = str.maketrans(delete_dict)
test_string = test_string.translate(table)

# printing resultant string
print ("Resultant list is : " + str(test_string))
```

**输出:**

```
Original String : Ge;ek*s:fo!r;Ge*e*k:s!
Resultant list is : GeeksforGeeks

```

**方法#4:使用过滤器()**
这是执行该任务的又一个解决方案。使用 lambda 函数，filter 函数可以移除所有的 bad_chars 并返回想要的精确字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate
# removal of bad_chars
# using filter()

# initializing bad_chars_list
bad_chars = [';', ':', '!', "*"]

# initializing test string
test_string = "Ge;ek*s:fo!r;Ge*e*k:s!"

# printing original string
print("Original String : " + test_string)

# using filter() to
# remove bad_chars
test_string = ''.join((filter(lambda i: i not in bad_chars, test_string)))
# printing resultant string
print("Resultant list is : " + str(test_string))
```

**输出:**

```
Original String : Ge;ek*s:fo!r;Ge*e*k:s!
Resultant list is : GeeksforGeeks

```