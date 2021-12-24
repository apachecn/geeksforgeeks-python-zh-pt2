# Python 程序检查字符串是否至少有一个字母和一个数字

> 原文:[https://www . geesforgeks . org/python-程序检查字符串是否至少有一个字母和一个数字/](https://www.geeksforgeeks.org/python-program-to-check-if-a-string-has-at-least-one-letter-and-one-number/)

给定 Python 中的一个字符串。任务是检查字符串是否至少有一个字母(字符)和一个数字。如果给定的字符串完全满足上述条件，则返回“真”，否则返回“假”(不带引号)。
**例:**

```
Input: welcome2ourcountry34
Output: True

Input: stringwithoutnum
Output: False
```

**方法:**
方法很简单我们将使用循环和两个标志来表示字母和数字。这些标志将检查字符串是否包含字母和数字。最后，我们将取两个标志的“与”来检查两者是否都是真的。可以使用 isalpha()方法在 Python String 中检查字母，使用 isdigit()方法检查数字。

## 蟒蛇 3

```
def checkString(str):

    # initializing flag variable
    flag_l = False
    flag_n = False

    # checking for letter and numbers in
    # given string
    for i in str:

        # if string has letter
        if i.isalpha():
            flag_l = True

        # if string has number
        if i.isdigit():
            flag_n = True

    # returning and of flag
    # for checking required condition
    return flag_l and flag_n

# driver code
print(checkString('thishasboth29'))
print(checkString('geeksforgeeks'))
```

**输出**:

```
True
False
```