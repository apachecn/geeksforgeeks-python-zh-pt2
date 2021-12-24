# 海绵宝宝嘲讽文字生成器–Python

> 原文:[https://www . geesforgeks . org/海绵宝宝-嘲讽-文本-生成器-python/](https://www.geeksforgeeks.org/spongebob-mocking-text-generator-python/)

海绵宝宝嘲讽文字(海绵宝宝)是一种字母大小写随机的书写方式。它在网络社区中被用来嘲笑某些东西。这篇文章起源于海绵宝宝卡通系列的一个迷因。

**示例:**

```py
Input : The quick brown fox jumps over the lazy dog.
Output : tHE QuiCK BrOWN fOX juMps over tHe lAzY dOG.

Input : This sentence is to test the function.
Output : This seNtENce is TO TeST THE funcTiON.

```

**算法:**

1.  按字符处理输入字符串。
2.  使用`isalpha()`方法检查字符是否为字母。
3.  使用`random.random()`方法生成一个 0 到 1 之间的随机数。
4.  如果生成的数字大于 0.5，则使用`upper()`方法将字符改为大写。
5.  如果生成的数字小于或等于 0.5，则使用`lower()`方法将字符更改为小写。

```py
# import the random library
import random

# Function to convert into spongemock
def spongemock(input_text):

    # variable declaration for the output text
    output_text = ""

    # check the cases for every individual character
    for char in input_text:

        # check if the character is an alphabet
        if char.isalpha():

            # convert to upper case
            if random.random() > 0.5:
                output_text += char.upper()

            # convert to lower case
            else:
                output_text += char.lower()

        # if character is not and alphabet
        # add it as it is
        else:
            output_text += char

    # return the output_text
    return output_text

# Driver code
if __name__=="__main__":
    input_text1 = "The quick brown fox jumps over the lazy dog."
    input_text2 = "This sentence is to test the function."
    print(spongemock(input_text1))
    print(spongemock(input_text2))
```

**输出:**

```py
tHe qUICk BrOWn fox jUMPs oVEr thE lAZy dOG.
THIS seNTEncE IS tO TesT tHe FuNcTIOn.

```

上面的代码生成大小写相等的文本。如果我们想倾斜天平偏向一边，我们可以将`random.random()`方法切换为`random.triangular()`方法。

```py
# import the random library
import random

def skewupper():
    low = 0
    high = 100
    mode = 80
    return random.triangular(low, high, mode)

def skewlower():
    low = 0
    high = 100
    mode = 20
    return random.triangular(low, high, mode)

# Function to convert into spongemock
# with more upper case charcters
def spongemockupper(input_text):
    output_text = ""
    for char in input_text:
        if char.isalpha():
            if skewupper() > 50:
                output_text += char.upper()
            else:
                output_text += char.lower()
        else:
            output_text += char
    return output_text

# Function to convert into spongemock
# with more lower case charcters
def spongemocklower(input_text):
    output_text = ""
    for char in input_text:
        if char.isalpha():
            if skewlower() > 50:
                output_text += char.upper()
            else:
                output_text += char.lower()
        else:
            output_text += char
    return output_text

# Driver code
if __name__=="__main__":
    input_text1 = "The quick brown fox jumps over the lazy dog."
    print("Spongemock text with more upper case characters :\n" + 
                                    spongemockupper(input_text1))

    print("\nSpongemock text with more lower case characters :\n" + 
                                      spongemocklower(input_text1))
```

**输出:**

```py
Spongemock text with more upper case characters :
ThE qUICK BROwN FOX jUMPs OVeR THE lazy DoG.

Spongemock text with more lower case characters :
The qUick BrOwn fOX JuMPs oveR the LaZy DOg.
```