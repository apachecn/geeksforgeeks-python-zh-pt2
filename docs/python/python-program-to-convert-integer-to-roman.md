# Python 程序将整数转换为罗马

> 原文:[https://www . geesforgeks . org/python-program-convert-integer-to-Roman/](https://www.geeksforgeeks.org/python-program-to-convert-integer-to-roman/)

给定一个整数，任务是编写一个 Python 程序，将整数转换为罗马数字。

**示例:**

```py
Input: 5
Output: V

Input: 9
Output: IX

Input: 40
Output: XL

Input:  1904
Output: MCMIV
```

**下表显示了罗马符号列表，包括其相应的整数值:**

<figure class="table">

| **符号** | **值** |
| --- | --- |
| 我 | one |
| 注入静脉的 | four |
| V | five |
| 离子交换 | nine |
| X | Ten |
| 特大号 | Forty |
| L | Fifty |
| XC | Ninety |
| C | One hundred |
| 激光唱片 | four hundred |
| D | Five hundred |
| 厘米 | Nine hundred |
| M | One thousand |

</figure>

想法是分别转换给定数字的单位、十、百和千位。如果数字是 0，那么就没有对应的罗马数字符号。数字 4 和 9 的转换与其他数字有点不同，因为这些数字遵循减法符号。

**将整数值转换为罗马数字的算法**

将给定的数字与 1000、900、500、400、100、90、50、40、10、9、5、4、1 的基本值进行比较。刚好小于或等于给定数字的基值将是初始基值(最大基值)，将数字除以其最大基值，相应的基符号将被重复商次，余数将成为未来除法和重复的数字。该过程将重复进行，直到数字变为零。

## **方法 1:**

*   最初数字= 3549，因为 3549 > = 1000；最大基础值最初为 1000。并除以 3549/1000。商= 3，余数=549。相应的符号 M 将重复三次。
*   现在，数字变成 549 和 1000 > 549 >= 500，最大的基础值将是 500，然后除以 549/500。商= 1，余数=49。相应的符号 D 将重复一次。
*   现在，数字= 49 和 50 > 49 >= 40，最大的基础值是 40。然后除以 49/40。商= 1，余数= 9。相应的符号 XL 将重复一次。
*   现在，数字= 9 和 10> 9 >= 9，最大的基值是 9。然后除以 9/9。商= 1，余数= 0。相应的符号 IX 将重复一次。
*   最后，数字变成 0，算法到此为止。得到的输出是 MMMDXLIX。

**下面的例子展示了上述算法的实现:**

## 蟒蛇 3

```py
# Python3 program to convert
# integer value to roman values

# Function to convert integer to Roman values
def printRoman(number):
    num = [1, 4, 5, 9, 10, 40, 50, 90,
        100, 400, 500, 900, 1000]
    sym = ["I", "IV", "V", "IX", "X", "XL",
        "L", "XC", "C", "CD", "D", "CM", "M"]
    i = 12

    while number:
        div = number // num[i]
        number %= num[i]

        while div:
            print(sym[i], end = "")
            div -= 1
        i -= 1

# Driver code
if __name__ == "__main__":
    number = 3549
    print("Roman value is:", end = " ")
    printRoman(number)
```

**输出:**

```py
Roman value is: MMMDXLIX
```

## **方法二:**

在这个方法中，我们首先要观察问题。问题陈述中给出的数字最多可以是 4 位数。解决这个问题的思路是:

*   将给定的数字在不同的地方分成数字，如一、二、百或千。
*   从千位开始打印相应的罗马值。例如，如果千位的数字是 3，那么打印罗马数字 3000。
*   重复第二步，直到我们到达某人的位置。

假设输入的数字是 3549。所以，从千之地开始，我们将开始印刷罗马版。在这种情况下，我们将按以下顺序打印:

*   相当于 3000 的罗马货币
*   相当于 500 的罗马货币
*   相当于 40 的罗马数字
*   相当于 9 的罗马数字

所以，输出会是: **MMMDXLIX**

**下面的例子展示了上述方法的实现:**

## 蟒蛇 3

```py
# Python3 program for above approach

# Function to calculate Roman values
def intToRoman(num):

    # Storing roman values of digits from 0-9
    # when placed at different places
    m = ["", "M", "MM", "MMM"]
    c = ["", "C", "CC", "CCC", "CD", "D",
         "DC", "DCC", "DCCC", "CM "]
    x = ["", "X", "XX", "XXX", "XL", "L",
         "LX", "LXX", "LXXX", "XC"]
    i = ["", "I", "II", "III", "IV", "V",
         "VI", "VII", "VIII", "IX"]

    # Converting to roman
    thousands = m[num // 1000]
    hundereds = c[(num % 1000) // 100]
    tens = x[(num % 100) // 10]
    ones = i[num % 10]

    ans = (thousands + hundereds +
           tens + ones)

    return ans

# Driver code
if __name__ == "__main__":
    number = 3549
    print(intToRoman(number))
```

**输出:**

```py
MMMDXLIX
```

## **方法 3:**

在这种方法中，我们考虑数字的主要有效数字。例:在 1234 中，主要的有效数字是 1。类似地，在 345 中它是 3。为了提取出主要的有效数字，我们需要保持一个除数(让我们称之为 div)，比如 1000 代表 1234(因为 1234 / 1000 = 1)，100 代表 345 (345 / 100 = 3)。另外，让我们维护一个名为罗马数字= { 1:I，5:V，10:X，50:L，100:C，500:D，1000:M }的字典

**下面的例子展示了上述算法的实现:**

## 蟒蛇 3

```py
# Python 3 program to convert integer
# number to Roman values
import math

def integerToRoman(A):
    romansDict = \
        {
            1: "I",
            5: "V",
            10: "X",
            50: "L",
            100: "C",
            500: "D",
            1000: "M",
            5000: "G",
            10000: "H"
        }

    div = 1
    while A >= div:
        div *= 10

    div /= 10

    res = ""

    while A:

        # main significant digit extracted
        # into lastNum
        lastNum = int(A / div)

        if lastNum <= 3:
            res += (romansDict[div] * lastNum)
        elif lastNum == 4:
            res += (romansDict[div] +
                        romansDict[div * 5])
        elif 5 <= lastNum <= 8:
            res += (romansDict[div * 5] +
            (romansDict[div] * (lastNum - 5)))
        elif lastNum == 9:
            res += (romansDict[div] +
                        romansDict[div * 10])

        A = math.floor(A % div)
        div /= 10

    return res

# Driver code
print("Roman value for the integer is:"
                + str(integerToRoman(3549)))
```

**输出:**

```py
Roman value for the integer is: MMMDXLIX
```