# Python 令牌和字符集

> 原文:[https://www . geesforgeks . org/python-令牌和字符集/](https://www.geeksforgeeks.org/python-tokens-and-character-sets/)

Python 是一种通用的高级编程语言。它的设计强调代码的可读性，它的语法允许程序员用更少的代码行来表达他们的概念，这些代码被称为脚本。这些脚本包含字符集、令牌和标识符。在本文中，我们将了解这些字符集、标记和标识符。

### 字符集

字符集是编程语言在脚本中可接受的一组有效字符。在这种情况下，我们谈论的是 Python 编程语言。因此，Python 字符集是 Python 语言可以识别的有效字符集。这些是我们在用 Python 编写脚本时可以使用的字符。Python 支持所有 ASCII / Unicode 字符，包括:

*   **字母:**所有大写(a-z)和小写(A-Z)字母。
*   **数字:**所有数字 0-9。
*   **特殊符号:** Python 支持各种特殊符号，如“‘l；: !~ @ # $ % ^ `&*()_+–= { }[]\。
*   **空格:**制表符、空格、换行符和回车等空格。
*   **其他:**构成 Python 字符集的 Python 支持所有 ASCII 和 UNICODE 字符。

### 代币

令牌是 python 程序中最小的独立单元。程序中的所有语句和指令都是用令牌构建的。python 中的各种标记有:

**1。关键词:**关键词是在编程语言中具有某种特殊含义或意义的词。它们不能用作变量名、函数名或任何其他随机用途。它们因其特殊功能而被使用。在 Python 中，我们有 33 个关键词，其中一些是: *try，False，True，class，break，contInue，as，assert，while，for，in，raise，except，or，not，if，elif，print，import，*等。

## 蟒 3

```
# for loop
for x in range(1, 9):

    # Print the value of x
    print(x)

    # Check if the value of x is less than 6
    # Here if the value of x is less than 6 
    # then the loop will continue
    # Here, if, continue, else, break, 
    # for loop are keywords
    if x < 6: 
        continue

    # If i greather then 6 then break loop
    else:
        break
```

**输出:**

```
1
2
3
4
5
6
```

**2。标识符:**标识符是任何变量、函数、类、列表、方法等的名称。为了他们的身份。Python 是一种区分大小写的语言，它有一些命名标识符的规则和规定。这里有一些命名标识符的规则:-

*   As mentioned above, Python is case sensitive. So the case is very important when naming identifiers. Therefore, **geek** and **geek** are two different identifiers.
*   Identifiers begin with uppercase letters (a-z), lowercase letters (A-Z) or underscores (_). It cannot start with any other role.
*   Besides letters and underscores, numbers can also be part of an identifier, but not its first character.
*   Any other special characters or spaces are strictly prohibited in the identifier.
*   The identifier cannot be a keyword.

> **例如:**一些有效的标识符有 gfg、GeeksforGeeks、_geek、mega12 等。而 91road，#tweet，我是，等等。不是有效的标识符。

## 蟒 3

```
# Here GFG and b are the identifier 
GFG = 'Hello'
b = "Geeks"

# Driver code
print(GFG)
print(b)
```

**输出:**

```
Hello
Geeks
```

**3。文字或值:**文字是源代码中使用的固定值或数据项。Python 支持不同类型的文字，例如:

**(i)字符串文字:**用单引号、双引号或三引号书写的文本代表 Python 中的字符串文字。例如:“计算机科学”、“萨姆”等。我们还可以使用三重引号来编写多行字符串。

## 蟒蛇 3

```
# String Literals
a = 'Hello'
b = "Geeks"
c = '''Geeks for Geeks is a 
        learning platform'''

# Driver code
print(a)
print(b)
print(c)
```

**Output**

```
Hello
Geeks
Geeks for Geeks is a 
        learning platform
```

**(二)字符文字:**字符文字也是一种字符串文字类型，其中字符用单引号或双引号引起来。

## 蟒 3

```
# Character Literals
a = 'G'
b = "W"

# Driver code
print(a)
print(b)
```

**输出:**

```
G
W
```

**(三)数字文字:**这些是以数字形式书写的文字。Python 支持以下数字文字:

*   **Integer text:** It includes positive and negative numbers and 0\. Does not include the decimal part. It can also include binary, decimal, octal and hexadecimal characters.
*   **float literal:** It includes both positive and negative real numbers. It also includes the decimal part.
*   **plural literal:** contains a+bi numeral, where a represents the real part and b represents the plural part.

## 蟒 3

```
# Numeric Literals
a = 5
b = 10.3
c = -17

# Driver code
print(a)
print(b)
print(c)
```

**输出**

```
5
10.3
-17
```

**(四)布尔文字:**布尔文字在 Python 中只有两个值。这些是真和假。

T5】蟒 3T7

```
# Boolean Literals
a = 3
b = (a == 3)
c = True + 10

# Driver code
print(a, b, c)
```

T8T10**输出**T1

**(五)特殊文字:** Python 有一个特殊的文字“无”。它用来表示没有东西，没有价值，或者没有价值。

T5】蟒 3T7

```
# Special Literals
var = None
print(var)
```

T8T10**输出**T1

**(六)文字集合:**python 中的文字集合包括列表、元组、字典和集合。

1.  **List:** This is a list of elements in square brackets separated by commas. These variables can be of any data type or can be changed.
2.  **tuple:** is also a comma-separated list of elements or values in parentheses. These values can be of any data type, but cannot be changed.
3.  **Dictionary:** is an unordered set of key-value pairs.
4.  **Set:** is an unordered set of elements in curly braces "{}".

## 蟒 3

```
# Literals collections
# List
my_list = [23, "geek", 1.2, 'data'] 

# Tuple
my_tuple = (1, 2, 3, 'hello')   

# Dictionary
my_dict = {1:'one', 2:'two', 3:'three'}   

# Set
my_set = {1, 2, 3, 4}  

# Driver code
print(my_list)
print(my_tuple)
print(my_dict)
print(my_set)
```

**输出**

```
[23, 'geek', 1.2, 'data']
(1, 2, 3, 'hello')
{1: 'one', 2: 'two', 3: 'three'}
{1, 2, 3, 4}
```

**4。运算符:**这些是负责在表达式中执行操作的标记。应用操作的变量称为*操作数。*运算符可以是一元或二元。一元运算符是作用于单个操作数的运算符，如补码运算符等。而二进制运算符需要两个操作数才能运算。

## python 3

```
# Operators
a = 12

 # Unary operator
b = ~ a 

# Binary operator
c = a+b   

# Driver code
print(b)
print(c)
```

**输出**

```
-13
-1
```

**5。标点符号:**这些是 Python 中用来组织结构、语句和表达式的符号。标点符号有:[]{ }()@-=+= * =/=/= * * = = =等。