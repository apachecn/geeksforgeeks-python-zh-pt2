# Python 程序打印代表整数的字节数组

> 原文:[https://www . geesforgeks . org/python-program-to-print-一个代表整数的字节数组/](https://www.geeksforgeeks.org/python-program-to-print-an-array-of-bytes-representing-an-integer/)

给定一个整数 **N** ，任务是编写一个 Python 程序，将这个数字的字节表示为一个数组。

一个字节是一组 8 位。任何整数都可以用字节和位的形式表示。我们通常用十六进制代码来表示一个字节。一个十六进制字符可以代表 4 位，因此一对十六进制字符用来代表一个字节。

**示例:**

> **输入:** N = 543
> 
> **输出:** ['0x2 '，' 0x1f']
> 
> **说明:** 543 可以用二进制表示为 1000011111，二进制可以分组为(10)(00011111)，每组代表一个字节。以十六进制形式，该数字将是(0x02)(0x1F)。
> 
> **输入:** N = 17292567
> 
> **输出:** ['0x1 '，' 0x7 '，' 0xdd '，' 0x17']
> 
> **说明:** 17292567 在二进制中可以表示为 10000111110110100010111，二进制可以分组为(1)(00000111)(11011101)(00010111)，每组代表一个字节。以十六进制形式，该数字将是(0x1)、(0x7)、(0xdd)、(0x17)。

**方法 1(手动转换):**

就像我们把十进制数转换成二进制数一样，我们可以把它转换成一个以 256 为基数的数，这样我们就可以得到代表给定数字节的 8 位数。

下面是实现上述方法的代码:

## 蟒蛇 3

```
n = 17292567

# Initialize the empty array
array = []

# Get the hexadecimal form
while(n):
    r = n % 256
    n = n//256
    array.append(hex(r))

# Reverse the array to get the MSB to left
array.reverse()
print(array)
```

**Output**

```
['0x1', '0x7', '0xdd', '0x17']
```

**方法 2(使用** ***至 _bytes()*** **方法):**

我们还可以使用 *to_bytes(length，byteorder)* 方法将数字转换为十六进制字符串。但是这个函数的问题是，在打印时，十六进制代码可以转换成 ASCII 编码方案中相应的字符。为了克服这一点，我们可以在这个方法上使用 hex()方法。它需要两个参数，'*长度*'是数组的大小，' *byteorder'* 是字节的顺序，其中“*大”*表示 MSB 将在左边，“*小”*表示 MSB 将在右边。

下面是实现上述方法的代码:

## 蟒蛇 3

```
import math

n = 543

# Calculate the length of array
size = int(math.log(n, 256))+1

# Use the method to_bytes() with "big" 
# or "little" property We need to apply
# hex() method to avoid the conversion 
# into ASCII letters
hexForm = n.to_bytes(size, "big").hex()

# Append 8 bits together ie pair of 4 bits to get a byte
array = []
for i in range(0, len(hexForm), 2):
    array.append('0x'+hexForm[i]+hexForm[i+1])
print(array)
```

**Output**

```
['0x02', '0x1f']
```

**方法 3(使用字符串格式命令):**

在 Python 中，有一个字符串命令“%x”，可以将给定的整数转换为十六进制格式。我们可以用它来获得想要的输出。

下面是实现上述方法的代码:

## 蟒蛇 3

```
n = 8745

# Get string representation of hex code
hexcode = "%x" % n

# Pad an extra 0 is length is odd
if len(hexcode) & 1:
    hexcode = "0"+hexcode

array = []
for i in range(0, len(hexcode), 2):
    array.append('0x'+hexcode[i]+hexcode[i+1])
print(array)
```

**Output**

```
['0x22', '0x29']
```