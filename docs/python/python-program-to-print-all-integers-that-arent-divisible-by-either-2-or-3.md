# 打印所有不能被 2 或 3 整除的整数的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-print-all-integers-不能被 2 或 3 整除/](https://www.geeksforgeeks.org/python-program-to-print-all-integers-that-arent-divisible-by-either-2-or-3/)

我们可以输入一组整数，并通过检查 2 和 3 的整数的余数来检查这个范围内哪些整数不能被 2 或 3 整除。

**示例:**

```py
Input: 10
Output: Numbers not divisible by 2 and 3
1
5
7

```

**方法 1** :我们使用 and 子句检查数字是否不能被 2 和 3 整除，然后输出数字。

## 蟒蛇 3

```py
# input the maximum number to
# which you want to send
max_num = 20

# starting numbers from 0
n = 1

# run until it reaches maximum number
print("Numbers not divisible by 2 and 3")
while n <= max_num:

    # check if number is divisible by 2 and 3
    if n % 2 != 0 and n % 3 != 0:
        print(n)

    # incrementing the counter
    n = n+1
```

**输出:**

```py
Numbers not divisible by 2 and 3
1
5
7
11
13
17
19
```

**方法 2** :我们遍历从 1 开始的奇数，因为偶数可以被 2 整除。因此，我们将循环的增加 2，只遍历奇数，并检查哪一个不能被 3 整除。这种方法比前一种更好，因为它只迭代指定范围内一半数量的元素。

下面的 Python 代码说明了这一点:

## 蟒蛇 3

```py
# input the maximum number to
# which you want to send
max_num = 40
print("Numbers not divisible by 2 or 3 : ")

# run until it reaches maximum number
# we increment the loop by +2 each time,
# since odd numbers are not divisible by 2
for i in range(1, max_num, 2):

    # check if number is not divisible by  3
    if i % 3 != 0:
        print(i)
```

**输出:**

```py
Numbers not divisible by 2 or 3 : 
1
5
7
11
13
17
19
23
25
29
31
35
37

```