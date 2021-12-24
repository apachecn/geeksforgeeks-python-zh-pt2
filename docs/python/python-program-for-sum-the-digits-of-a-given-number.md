# 给定数字总和的 Python 程序

> 原文:[https://www . geesforgeks . org/python-给定数字的总和程序/](https://www.geeksforgeeks.org/python-program-for-sum-the-digits-of-a-given-number/)

给定一个数字，任务是在 Python 中找到这个数字的数字总和。
**例:**

> 输入:n = 87
> 输出:15
> 输入:n = 111
> 输出:3

下面是数字求和的方法。
**方法-1:使用 str()和 int()方法。**:str()方法用于将数字转换为字符串。int()方法用于将字符串数字转换为整数。

将数字转换为字符串，并迭代字符串中的每个数字，在将每个数字转换为整数后，将每个迭代中的数字相加。

## 蟒蛇 3

```
# Python program to
# compute sum of digits in 
# number.

# Function to get sum of digits 
def getSum(n):

    sum = 0
    for digit in str(n): 
      sum += int(digit)      
    return sum

n = 12345
print(getSum(n))
```

**输出:**

```
15
```

**方法-2:使用 sum()方法。:**sum()方法用于列表中数字的求和。

使用 str()将数字转换为字符串，并分别使用 strip()和 map()方法剥离字符串并转换为数字列表。然后用 sum()方法求和。

## 蟒蛇 3

```
# Python program to
# compute sum of digits in 
# number.

# Function to get sum of digits 
def getSum(n):

    strr = str(n)
    list_of_number = list(map(int, strr.strip()))
    return sum(list_of_number)

n = 12345
print(getSum(n))
```

**输出:**

```
15
```

**方法-3:使用通用方法:**

*   拿到号码
*   声明一个变量来存储总和，并将其设置为 0
*   重复接下来的两个步骤，直到数字不为 0
*   借助余数“%”运算符，将数字除以 10，得到数字最右边的数字，并将其相加。
*   借助“//”运算符将数字除以 10
*   打印或返回总和

**A .迭代方法:**

## 蟒蛇 3

```
# Python 3 program to
# compute sum of digits in 
# number.

# Function to get sum of digits 
def getSum(n):

    sum = 0
    while (n != 0):

        sum = sum + (n % 10)
        n = n//10

    return sum

n = 12345
print(getSum(n))
```

**输出:**

```
15
```

**B .递归方法:**

## 蟒蛇 3

```
# Python program to compute
# sum of digits in number.

def sumDigits(no):
    return 0 if no == 0 else int(no % 10) + sumDigits(int(no / 10)) 

# Driver code
n = 12345
print(sumDigits(n))
```

**输出:**

```
15
```