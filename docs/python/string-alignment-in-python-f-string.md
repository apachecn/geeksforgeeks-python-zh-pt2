# Python f-String 中的字符串对齐方式

> 原文:[https://www . geesforgeks . org/string-alignment-in-python-f-string/](https://www.geeksforgeeks.org/string-alignment-in-python-f-string/)

Python 中的文本对齐对于打印出干净的格式化输出很有用。有时，要打印的数据长度不同，这使得打印时看起来很乱。使用**字符串对齐**可以通过将对齐定义为左对齐、右对齐或中心对齐，并定义为字符串保留的空间(宽度)来对齐输出字符串。

**方法:**我们将使用 f 字符串来格式化文本。输出字符串对齐的语法由“<”、“>”、'^'定义，后面是宽度数字。

**示例 1 :** 对于左对齐输出字符串语法，定义“<”后跟宽度数字。

```py
# here 20 spaces are reserved for the 
# particular output string. And the string
# is printed on the left side
print(f"{'Left Aligned Text' : <20}")
```

**输出:**

```py
Left Aligned Text
```

**示例 2 :** 对于右对齐输出字符串语法，定义“>”后跟宽度数字。

```py
# here 20 spaces are reserved for the 
# particular output string. And the string
# is printed on the right side
print(f"{'Right Aligned Text' : >20}")
```

**输出:**

```py
  Right Aligned Text
```

**示例 3 :** 对于中心对齐输出字符串语法，定义'^'后跟宽度数字。

```py
# here 20 spaces are reserved for the 
# particular output string. And the string
# is printed in the middle
print(f"{'Centered' : ^10}")
```

**输出:**

```py
 Centered 
```

**示例 4 :** 以对齐格式打印变量

```py
# assigning strings to the variables
left_alignment = "Left Text"
center_alignment = "Centered Text"
right_alignment = "Right Text"

# printing out aligned text
print(f"{left_alignment : <20}{center_alignment : ^15}{right_alignment : >20}")
```

**Output :**

```py
Left Text            Centered Text           Right Text

```

**示例 5 :** 以对齐的列外观打印出多个列表值。

```py
# assigning list values to the variables
names = ['Raj', 'Shivam', 'Shreeya', 'Kartik']
marks = [7, 9, 8, 5]
div = ['A', 'A', 'C', 'B']
id = [21, 52, 27, 38]

# printing Aligned Header
print(f"{'Name' : <10}{'Marks' : ^10}{'Division' : ^10}{'ID' : >5}")

# printing values of variables in Aligned manner
for i in range(0, 4):
    print(f"{names[i] : <10}{marks[i] : ^10}{div[i] : ^10}{id[i] : >5}")
```

**Output :**

```py
Name        Marks    Division    ID
Raj           7         A        21
Shivam        9         A        52
Shreeya       8         C        27
Kartik        5         B        38

```