# Python 程序以词法顺序生成字母列表

> 原文:[https://www . geesforgeks . org/python-program-to-generate-list-按词汇顺序排列的字母/](https://www.geeksforgeeks.org/python-program-to-generate-a-list-of-alphabets-in-lexical-order/)

**先决条件:**T2【chr()

以下方法解释了如何使用 chr()方法动态生成带有词法(字母)顺序字母的 python 列表。

**进场:**

这两种方法的核心概念几乎相同，它们只是在实现上有所不同:

1.  验证字母表的大小(大小=26)。
2.  如果尺寸> 26，则改为 26。
3.  如果 size≤0，该函数没有任何意义，为了使其有意义，请将 size 设置为 26。
4.  使用 chr()使用以下任一方法生成列表。

**方法 1:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

## 蟒蛇 3

```
# function to get the list of alphabets
def generateAlphabetListDynamically(size = 26):
  size = 26 if (size > 26 or size <= 0) else size

  # Empty list 
  alphabetList = []

  # Looping from 0 to required size 
  for i in range(size):
    alphabetList.append(chr(65 + i))

  # return the generated list
  return alphabetList

alphabetList = generateAlphabetListDynamically()
print('The alphabets in the list are:', *alphabetList)
```

**输出:**

> 列表中的字母是:A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

**方法二:**使用[列表理解](https://www.geeksforgeeks.org/comprehensions-in-python/)

## 蟒蛇 3

```
def generateAlphabetListDynamically(size=26):
    size = 26 if (size > 26 or size <= 0) else size

    # Here we are looping from 0 to upto specified size
    # 65 is added because it is ascii equivalent of 'A'
    alphabetList = [chr(i+65) for i in range(size)]

    # returning the list
    return alphabetList

# Calling the function to get the alphabets
alphabetList = generateAlphabetListDynamically()
print('The alphabets in the list are:', *alphabetList)
```

**输出:**

> 列表中的字母是:A B C D E F G H I J K L M N O P Q R S T U V W X Y Z