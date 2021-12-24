# Python 程序统计字符串中的空格数

> 原文:[https://www . geesforgeks . org/python-program-to-count-number-in-string/](https://www.geeksforgeeks.org/python-program-to-count-the-number-of-spaces-in-string/)

给定一个字符串，任务是编写一个 Python 程序来计算字符串中的空格数。

**示例:**

```
Input: "my name is geeks for geeks"
Output: number of spaces = 5

Input: "geeksforgeeks"
Output: number of spaces=0
```

**进场:**

*   来自用户的输入字符串
*   用零初始化计数变量
*   从 0 到字符串长度运行 for 循环 I
*   在循环内部，检查 s[i] ==是否为空，然后将计数增加 1
*   循环外部，打印计数

**例 1:**

## 蟒蛇 3

```
# create function that
# return space count
def check_space(string):

    # counter
    count = 0

    # loop for search each index
    for i in range(0, len(string)):

        # Check each char
        # is blank or not
        if string[i] == " ":
            count += 1

    return count

# driver node
string = "Welcome to geeksforgeeks"

# call the function and display
print("number of spaces ",check_space(string))
```

**输出:**

```
number of spaces  2
```

**例 2:**

## 蟒蛇 3

```
# create function that
# return space count
def check_space(string):

    # counter
    count = 0

    # loop for search each index
    for i in string:

        # Check each char
        # is blank or not
        if i == " ":
            count += 1

    return count

# driver node
string = "Welcome to geeksforgeeks, Geeks!"

# call the function and display
print("number of spaces ",check_space(string))

```

**输出:**

```
number of spaces  3
```

**示例 3:使用 count()函数。**

## 蟒蛇 3

```
# Create function that
# return space count
def check_space(Test_string):
    return Test_string.count(" ")

# Driver function
if __name__ == "__main__":
    Test_string = "Welcome to geeksforgeeks, Geeks!"

    # Call the function and display
    print(f"Number of Spaces: {check_space(Test_string)}")
```

**输出:**

```
Number of Spaces: 3
```