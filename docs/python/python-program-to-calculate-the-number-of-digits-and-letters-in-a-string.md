# Python 程序计算字符串中数字和字母的个数

> 原文:[https://www . geesforgeks . org/python-计算字符串中数字和字母数量的程序/](https://www.geeksforgeeks.org/python-program-to-calculate-the-number-of-digits-and-letters-in-a-string/)

**先决条件:** [是数值()方法–Python](https://www.geeksforgeeks.org/python-string-isnumeric-application/)

给定一个包含数字和字母的字符串，任务是编写一个 Python 程序来计算字符串中数字和字母的数量。以下模块表达了其背后的基本思想:

```
Input: string = "geeks2for3geeks"
Output: total digits = 2 and total letters = 13

Input: string = "python1234"
Output: total digits = 4 and total letters = 6

Input: string = "co2mpu1te10rs"
Output: total digits = 4 and total letters = 9
```

#### **第一次进场**

这里的想法是通过遍历所有字符并检查字符是全数字还是全字母来解决这个问题。

**程序:**

## 蟒蛇 3

```
# define all digits as string
all_digits = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']

# define all letters
all_letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l',
               'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

# given string
string = "geeks2for3geeks"

# initialized value
total_digits = 0
total_letters = 0

# iterate through all characters
for s in string:

    # if character found in all_digits then increment total_digits by one
    if s in all_digits:
        total_digits += 1

    # if character found in all_letters then increment total_letters by one
    elif s in all_letters:
        total_letters += 1

print("Total letters found :-", total_letters)
print("Total digits found :-", total_digits)
```

**输出:**

```
Total letters found :- 13
Total digits found :- 2
```

#### **优化方法**

我们可以不检查 all_letters 中的字符，而是检查:

*   如果在所有数字中找到字符，则将 total_digits 值增加 1
*   如果不是，则表示字符是一个字母，将 total_letters 值增加 1

**程序:**

## 蟒蛇 3

```
# define all digits as string
all_digits = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']

# define all letters
all_letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l',
               'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

# given string
string = "geeks2for3geeks"

# initialized value
total_digits = 0
total_letters = 0

# iterate through all characters
for s in string:

    # if character found in all_digits then increment total_digits by one
    if s in all_digits:
        total_digits += 1

    # if character not found in all_digits then increment total_letters by one
    else:
        total_letters += 1

print("Total letters found :-", total_letters)
print("Total digits found :-", total_digits)
```

**输出:**

```
Total letters found :- 13
Total digits found :- 2
```

#### **第二种方法(更优化的方法)**

这里的思路是通过迭代所有字符，使用 isnumeric() 函数检查字符是字母还是数字来解决这个问题。如果 isnumeric 为 True，则表示字符是数字，否则字符是字母。

**程序:**

## 蟒蛇 3

```
# given string
string = "python1234"

# initialized value
total_digits = 0
total_letters = 0

# iterate through all characters
for s in string:

    # if character is digit (return True)
    if s.isnumeric():
        total_digits += 1

    # if character is letter (return False)
    else:
        total_letters += 1

print("Total letters found :-", total_letters)
print("Total digits found :-", total_digits)
```

**输出:**

```
Total letters found :- 6
Total digits found :- 4
```