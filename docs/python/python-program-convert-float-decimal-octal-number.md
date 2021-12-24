# Python 程序将浮点数十进制转换为八进制数

> 原文:[https://www . geesforgeks . org/python-program-convert-float-十进制-八进制-number/](https://www.geeksforgeeks.org/python-program-convert-float-decimal-octal-number/)

Python 不支持任何将浮点十进制数轻松转换为八进制表示的内置函数。让我们手动操作。

**方法:**将一个有小数部分的十进制数转换成八进制，先将整数部分转换成八进制，再将小数部分转换成八进制，最后将两个结果结合起来得到最终答案。
对于整数部分，继续将数字除以 8，记下余数，直到且除非被除数小于 8，并将所有余数复制在一起。
对于小数部分，继续将小数部分乘以 8，直到和，除非我们剩下 0 作为小数部分。第一次相乘后，记下一个整数部分，然后再次将新值的小数部分乘以 8，并一直这样做，直到达到完美的数字。

> **以上步骤可以写成:**
> `7(base 10) = 7(base 8) and .16(base 10) = .1217(base 8)`
> 
> `Now, to get the octal of the decimal number 7.16, merge the two octal results.
> (7)10 = (7)8`
> 
>  `(0.16)10 = (0.1217...)8
> So, (7.16)10 = (7.1217...)8
> or, (7.16)10 = (7.1217)8 (approx. value)`

下面是实现:

```
# Python3 program to demonstrate
# octal type conversion

# Function returns the octal representation
# of the value passed as parameters. 'number'
# is floating point decimal number and 'places'
# is the number of decimal places
def float_octal(number, places = 3):

    # split() separates whole number and decimal 
    # part and stores it in two separate variables
    whole, dec = str(number).split(".")

    # Convert both whole number and decimal  
    # part from string type to integer type
    whole = int(whole)
    dec = int (dec)

    # Convert the whole number part to it's
    # respective octal form and remove the
    # "0o" from it.
    res = oct(whole).lstrip("0o") + "."

    # Iterate the number of times we want
    # the number of decimal places to be
    for x in range(places):

        # Multiply the decimal value by 8 and separate 
        # the whole number part and decimal part
        whole, dec = str((decimal_converter(dec)) * 8).split(".")

        # Convert the decimal part
        # to integer again
        dec = int(dec)

        # keep adding the integer parts 
        # received to the result variable
        res += whole

    return res

# Function converts the value passed as
# parameter to it's respective decimal
# representation
def decimal_converter(num):
    while num > 1:
        num /= 10
    return num

# Driver Code

# Take the user input for 
# the floating point number
n = input("Enter your floating point value : \n")

# Take user input for the number of decimal 
# places user would like the result as
p = int(input("Enter the number of decimal places of the result : \n"))

print(float_octal(n, places = p))
```

**输出:**

```
Enter your floating point value :
7.16

Enter the number of decimal places of the result :
10

7.1217273146

```

```
Enter your floating point value :
7.1234

Enter the number of decimal places of the result : 
5

7.07713

```