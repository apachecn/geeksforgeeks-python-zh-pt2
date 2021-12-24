# Python |从字符串中拆分多个字符

> 原文:[https://www . geesforgeks . org/python-split-多字符-from-string/](https://www.geeksforgeeks.org/python-split-multiple-characters-from-string/)

在编写代码或即兴发挥编程技能时，您肯定遇到过许多场景，您希望使用 Python 中的 **`.split()`** 不要一次只拆分一个字符，而是拆分多个字符。以此为例:

```py
"GeeksforGeeks, is an-awesome! website"
```

在上面使用 **`.split()`** 会导致

```py
['GeeksforGeeks, ', 'is', 'an-awesome!', 'website']
```

而期望的结果应该是

```py
['GeeksforGeeks', 'is', 'an', 'awesome', 'website']
```

在这篇文章中，我们将研究一些方法来达到同样的目的。

#### 使用 re.split()

这是一次拆分多个字符最有效、最常用的方法。为此，它使用正则表达式。

```py
# Python3 code to demonstrate working of 
# Splitting operators in String 
# Using re.split() 

import re

# initializing string
data = "GeeksforGeeks, is_an-awesome ! website"

# printing original string  
print("The original string is : " + data) 

# Using re.split() 
# Splitting characters in String 
res = re.split(', |_|-|!', data)

# printing result  
print("The list after performing split functionality : " + str(res)) 
```

**输出:**

> 原字符串是:GeeksforGeeks，is_an-awesome！网站
> 执行拆分功能后的列表:['GeeksforGeeks '，' is '，' an '，' awesome '，'网站'

第`re.split(', |_|-|!', data)`行告诉 Python 拆分字符上的变量数据:**、**或 **_** 或**–**或**！**。符号“ **|** ”代表或。

正则表达式中有一些符号被视为特殊符号，具有不同的功能。如果您希望在这样的符号上拆分，您需要使用“ **\** ”(反斜杠)来转义它。使用前需要转义的特殊字符列表:

```py
. \ + * ? [ ^ ] $ ( ) { } = !  | : -
```

**例如:**

```py
import re
newData = "GeeksforGeeks, is_an-awesome ! app + too"

# To split "+" use backslash
print(re.split(', |_|-|!|\+', newData))
```

**输出:**

```py
['GeeksforGeeks', ' is', 'an', 'awesome', ' app', 'too']
```

**注意:**想了解更多 regex [点击这里](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)。

#### 使用 re.findall()

这是一个有点神秘的形式，但节省时间。它也使用了像上面这样的正则表达式，但是它没有使用 **`.split()`** 方法，而是使用了一种叫做 **`.findall()`** 的方法。此方法查找所有匹配的实例，并在列表中返回每个实例。当您不知道要拆分的确切字符时，最好使用这种拆分方式。

```py
# Python3 code to demonstrate working of 
# Splitting operators in String 
# Using re.findall() 
import re

# initializing string  
data = "This, is - another : example?!"

# printing original string  
print("The original string is : " + data) 

# Using re.findall() 
# Splitting characters in String 
res = re.findall(r"[\w']+", data)

# printing result  
print("The list after performing split functionality : " + str(res)) 
```

**输出:**

> 原始字符串是:这是–另一个:示例？！
> 执行拆分功能后的列表:['这'，'是'，'另一个'，'示例']

这里的关键字`[\w']+`表示它将找到一个或多个字母或下划线(_)的所有实例，并在列表中返回它们。
**注意:** `[\w']+`在搜索字母和下划线时不会被下划线( **_** )分割。
**例如:**

```py
import re
testData = "This, is - underscored _ example?!"
print(re.findall(r"[\w']+", testData))
```

**输出:**

```py
['This', 'is', 'underscored', '_', 'example']
```

#### 使用替换()和拆分()

这是一种非常新颖的拆分方式。它没有使用正则表达式，效率很低，但仍然值得一试。如果你知道你想拆分的角色，就用空格代替，然后用 **`.split()`** :

```py
# Python code to demonstrate  
# to split strings 

# Initial string
data = "Let's_try, this now"

# printing original string  
print("The original string is : " + data) 

# Using replace() and split() 
# Splitting characters in String  
res = data.replace('_', ' ').replace(', ', ' ').split()

# Printing result
print("The list after performing split functionality : " + str(res)) 
```

**输出:**

> 原字符串为:Let’s _ try，this now
> 执行拆分功能后的列表:【“Let’s”、【try】、【this】、【now】

#### 字符类

关于字符描述的 Regex 备忘单

| 速记字符类 | 代表 |
| --- | --- |
| \d | 从 0 到 9 的任何数字 |
| \D | 任何不是 0 到 9 之间的数字的字符 |
| \w | 任何字母、数字或下划线字符 |
| \W | 任何不是字母、数字或下划线的字符 |
| \s | 任何空格、制表符或换行符 |
| \S | 任何不是空格、制表符或换行符的字符 |