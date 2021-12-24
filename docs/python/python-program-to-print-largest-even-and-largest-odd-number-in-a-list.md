# 打印列表中最大偶数和最大奇数的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到打印-列表中最大偶数和最大奇数/](https://www.geeksforgeeks.org/python-program-to-print-largest-even-and-largest-odd-number-in-a-list/)

给定一个列表。任务是打印列表中最大的偶数和最大的奇数。

**示例:**

```py
Input: 1 3 5 8 6 10 
Output:
Largest even number is  10 
Largest odd number is  5

Input: 123 234 236 694 809
Output:
Largest odd number is  809
Largest even number is  694
```

第一种方法使用两种方法，一种用于计算用户输入的数字列表中最大的偶数，另一种用于计算最大的奇数。每种方法分别打印最大的偶数和奇数。对于当前最大的偶数或奇数，我们为每个方法维护一个计数器，并检查该数是否能被 2 整除。因此，我们打印最大值。

## 蟒蛇 3

```py
class LargestOddAndEven:

    # find largest even number of
    # the list
    def largestEven(self, list):

        # counter for current largest
        # even number
        curr = -1

        for num in list:

            # converting number to integer
            # explicitly
            num = int(num)

            # even number is divisible by 2 and
            # if larger than current largest
            if(num % 2 == 0 and num > curr):

                # replace current largest even
                curr = num

        print("Largest even number is ", curr)

    # find largest odd number of the list
    def largestOdd(self, list):

        # current largest odd number
        currO = -1
        for num in list:

            # converting number to integer
            # explicitly
            num = int(num)

            # even number is divisible by 2 and
            # if larger than current largest
            if(num % 2 == 1 and num > currO):

                # replace current largest even
                currO = num

        print("Largest odd number is ", currO)

list_num = [1, 3, 5, 8, 6, 10]

# creating an object of class
obj = LargestOddAndEven()

# calling method for largest even number
obj.largestEven(list_num)

# calling method for largest odd number
obj.largestOdd(list_num)
```

**输出:**

```py
Largest even number is  10
Largest odd number is  5
```

第二种方法使用第一种方法的优化版本，其中我们计算一种方法本身的最大值。我们仍然维护两个计数器，但是遍历列表的 for 循环只运行一次。

## 蟒蛇 3

```py
class LargestOddAndEven:

    # find largest even number of the list
    def largestEvenandOdd(self, list):

        # counter for current largest even
        # number
        curr = -1

        # counter for current largest odd
        # number
        currO = -1
        for num in list:

            # converting number to integer
            # explicitly
            num = int(num)

            # even number is divisible by 2 and
            # if larger than current largest
            if(num % 2 == 0 and num > curr):

                # replace current largest even
                curr = num

            elif(num % 2 == 1 and num > currO):

                # replace current largest even
                currO = num

        print("Largest odd number is ", currO)
        print("Largest even number is ", curr)

# input a list of numbers
list_num = [123, 234, 236, 694, 809]

# creating an object of class
obj = LargestOddAndEven()

# calling method for largest even and odd number
obj.largestEvenandOdd(list_num)
```

**输出:**

```py
Largest odd number is  809
Largest even number is  694
```

#### 方法三:使用 python 中的列表理解和 max 函数:

*   使用 [**列表理解**](https://www.geeksforgeeks.org/comprehensions-in-python/) **将偶数和奇数存储在单独的列表中。**
*   打印 [**max()**](https://www.geeksforgeeks.org/python-max-function/) 的对应列表。

下面是上述方法的实现:

## 蟒蛇 3

```py
# Python program for the above approach

def printmax(lis):

    # Using list comprehension storing
    # even and odd numbers as separate lists
    even = [x for x in lis if x % 2 == 0]
    odd = [x for x in lis if x % 2 == 1]

    # printing max numbers in corresponding lists
    print("Largest odd number is ", max(odd))
    print("Largest even number is ", max(even))

# Input a list of numbers
lis = [123, 234, 236, 694, 809]

printmax(lis)

# This code is contributed by vikkycirus
```

**输出:**

```py
Largest odd number is  809

Largest even number is  694
```