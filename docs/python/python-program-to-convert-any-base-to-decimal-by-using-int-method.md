# Python 程序使用 int()方法将任意基数转换为十进制

> 原文:[https://www . geesforgeks . org/python-program-to-convert-any-base-to-decimal-by-int-method/](https://www.geeksforgeeks.org/python-program-to-convert-any-base-to-decimal-by-using-int-method/)

给定一个数及其基数，任务是将给定的数转换成其对应的十进制数。数字的基数可以是 0 到 9 和 A 到 z 之间的任何数字。其中 A 的值是 10，B 的值是 11，C 的值是 12，以此类推。

**示例:**

```
Input : '1011' 
base = 2 
Output : 11 

Input : '1A' 
base = 16
Output : 26

Input : '12345' 
base = 8
Output : 5349

```

**进场–**

*   给定字符串形式和基数的数字
*   现在调用内置函数 int('number '，base)，方法是将两个参数传递给 String 形式的任意基数和该数字的基数，并将值存储在 temp 中
*   打印温度值

## 蟒蛇 3

```
# Python program to convert any base
# number to its corresponding decimal
# number

# Function to convert any base number
# to its corresponding decimal number
def any_base_to_decimal(number, base):

    # calling the builtin function 
    # int(number, base) by passing 
    # two arguments in it number in
    # string form and base and store
    # the output value in temp
    temp = int(number, base)

    # printing the corresponding decimal
    # number
    print(temp)

# Driver's Code
if __name__ == '__main__' :
    hexadecimal_number = '1A'
    base = 16
    any_base_to_decimal(hexadecimal_number, base)
```

**输出:**

```
26
```