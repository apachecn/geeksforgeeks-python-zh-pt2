# Python |从元组列表中删除元组(如果不包含任何字符)

> 原文:[https://www . geesforgeks . org/python-从元组列表中移除元组-如果不包含任何字符/](https://www.geeksforgeeks.org/python-remove-tuple-from-list-of-tuples-if-not-containing-any-character/)

给定一个元组列表，任务是移除所有不包含任何字符值的元组。

**示例:**

```py
Input: [(', ', 12), ('...', 55),
        ('-Geek', 115), ('Geeksfor', 115),]

Output: [('-Geek', 115), ('Geeksfor', 115)]

```

**方法一:使用列表理解**

```py
# Python code to remove all those 
# elements from list of tuple
# which does not contains any alphabet.

# List initialization
List = [(', ', 12), ('Paras', 5),
        ('jain.', 11), ('...', 55),
        ('-Geek', 115), ('Geeksfor', 115),
        (':', 63), ('Data', 3), ('-', 15),
        ('Structure', 32), ('Algo', 80),]

# Using list comprehension 
out = [(a, b) for a, b in List 
       if any(c.isalpha() for c in a)]

# Printing output
print(out)
```

**Output:**

> [('Paras '，5)，(' jain '，11)、(“-Geek”，115)、(“Geeksfor”，115)、(“Data”，3)、(“Structure”，32)、(“Algo”，80)]

**方法 2:使用正则表达式**

```py
# Python code to remove all those 
# elements from list of tuple
# which does not contains any alphabet.

# List initialization
List = [(', ', 12), ('Paras', 5),
        ('jain.', 11), ('...', 55),
        ('-Geek', 115), ('Geeksfor', 115),
        (':', 63), ('Data', 3), ('-', 15),
        ('Structure', 32), ('Algo', 80),]

# Importing
import re

# Using regex
out = [t for t in List if re.search(r'\w', t[0])]

# Printing output
print(out)
```

**Output:**

> [('Paras '，5)，(' jain '，11)、(“-Geek”，115)、(“Geeksfor”，115)、(“Data”，3)、(“Structure”，32)、(“Algo”，80)]

 **方法三:使用滤镜和λ**

```py
# Python code to remove all those 
# elements from list of tuple
# which does not contains any alphabet.

# List initialization
List = [(', ', 12), ('Paras', 5),
        ('jain.', 11), ('...', 55),
        ('-Geek', 115), ('Geeksfor', 115),
        (':', 63), ('Data', 3), ('-', 15),
        ('Structure', 32), ('Algo', 80),]

# Using filter
out = filter(lambda x:any(c.isalpha()
                for c in x[0]), List)

# Converting in list
out = list(out)

# Printing output
print(out)
```

**Output:**

> [('Paras '，5)，(' jain '，11)、(“-Geek”，115)、(“Geeksfor”，115)、(“Data”，3)、(“Structure”，32)、(“Algo”，80)]