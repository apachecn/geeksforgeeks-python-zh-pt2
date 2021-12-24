# Python 程序打印给定列表中的所有强名称

> 原文:[https://www . geesforgeks . org/python-program-to-print-all-strong-numbers-in-给定列表/](https://www.geeksforgeeks.org/python-program-to-print-all-strong-numbers-in-given-list/)

给定一个列表，编写一个 Python 程序来打印该列表中所有强数字。

*强数是位数阶乘之和等于原数的数。*

***检查数字是否为强数的例子。***

```
***Input:** n = 145
**Output:** Yes
**Explanation:** 
Sum of digit factorials = 1! + 4! + 5!
                        = 1 + 24 + 120
                        = 145* 
```

***检查号码是否强的步骤:***

```
*1) Initialize sum of factorials as 0\. 
2) For every digit d, do following
   a) Add d! to sum of factorials.
3) If sum factorials is same as given 
   number, return true.
4) Else return false.* 
```

*让我们看看针对这个问题的 Python 程序:*

```
*# Python3 program to print 
# all strong numbers in a list. 

# Define a function for calculating
# factorial of a number
def factorial(number):

    fact = 1

    if number == 0 or number == 1 :
        return fact

    for i in range(2, number + 1) :
        fact *= i

    return fact

# Define a function for checking a 
# number is strong number or not
def find_strong_numbers(num_list):
    result = []

    # loop till list is not empty
    for num in num_list :
        sum = 0
        temp = num

        # loop till number is not zero
        while num != 0 :

            r = num % 10

            # function call
            sum += factorial(r)

            num //= 10

        # check number is strong or not
        if sum == temp:

            # adding number to the list
            result.append(temp)

    # return list of strong numbers   
    return result

# Driver Code
if __name__ == "__main__" :

    num_list = [145, 375, 100, 2, 10, 40585, 0]

    # function call
    strong_num_list = find_strong_numbers(num_list)

    # loop till list is not empty
    for strong_num in strong_num_list :
        print(strong_num, end =" ")
        *
```

***Output:**

```
145 2 40585 0

```*