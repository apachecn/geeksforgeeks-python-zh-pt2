# Python 中的 UwU 文本转换器

> 原文:[https://www.geeksforgeeks.org/uwu-text-convertor-in-python/](https://www.geeksforgeeks.org/uwu-text-convertor-in-python/)

**UwU** 用作表情符号，表示对可爱事物的反应。在这个表情符号中，“U”表示闭着眼睛，“w”表示紧咬的、激动的嘴唇。想象一下看到一些可爱的东西，比如宝宝可爱地打喷嚏，反应可以是 UwU，发音为“ooh-wooh”。

UwU text 是一种隐语类型，其中原始文本已被“UwUfied”。UwU 文字应该是比原文更可爱的版本。它很受某些在线社区的欢迎，主要是作为一种有趣的做法。

**示例:**

```
Input :  The quick brown fox jumps over the lazy dog.
Output : The quick bwown fox jumps ovew the wazy dog.

Input : Nooo! I was not late to work!
Output : Nyooo! I was nyot wate to wowk!
```

**算法:**

*   Change all' r' and' r' to' w' and' w' respectively.
*   Change all' l' and' l' to' w' and' w' respectively.
*   If the current character is' o' or' o' and the previous character is' m',' m',' n' or' n', then add' y' between the characters.
*   If the conditions of any character do not match, leave the character unchanged.

## 蟒 3

```
# Function to convert into UwU text
def generateUwU(input_text):

    # the length of the input text
    length = len(input_text)

    # variable declaration for the output text
    output_text = ''

    # check the cases for every individual character
    for i in range(length):

        # initialize the variables
        current_char = input_text[i]
        previous_char = ''&# 092;;&# 048;'

        # assign the value of previous_char
        if i > 0:
            previous_char = input_text[i - 1]

        # change 'L' and 'R' to 'W'
        if current_char == 'L' or current_char == 'R':
            output_text += 'W'

        # change 'l' and 'r' to 'w'
        elif current_char == 'l' or current_char == 'r':
            output_text += 'w'

        # if the current character is 'o' or 'O'
        # also check the previous character
        elif current_char == 'O' or current_char == 'o':
            if previous_char == 'N' or previous_char == 'n' or previous_char == 'M' or previous_char == 'm':
                output_text += "yo"
            else:
                output_text += current_char

        # if no case match, write it as it is
        else:
            output_text += current_char

    return output_text

# Driver code
if __name__=='__main__':
    input_text1 = "The quick brown fox jumps over the lazy dog."
    input_text2 = "Nooo ! I was not late to work !"
    print(generateUwU(input_text1))
    print(generateUwU(input_text2))
```

**输出:**

```
The quick bwown fox jumps ovew the wazy dog.
Nyooo! I was nyot wate to wowk!
```