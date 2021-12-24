# 在给定范围内寻找可被 7 整除的数和 5 的倍数的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序查找数字-给定范围内可被 7 整除的 5 的倍数/](https://www.geeksforgeeks.org/python-program-to-find-numbers-divisible-by-7-and-multiple-of-5-in-a-given-range/)

给定一个数字范围，任务是编写一个 Python 程序来查找可被 7 和 5 的倍数整除的数字。

**示例:**

```py
Input:Enter minimum 100
Enter maximum 200

Output:
105  is divisible by 7 and 5.
140  is divisible by 7 and 5.
175  is divisible by 7 and 5.

Input:Input:Enter minimum 29
Enter maximum 36

Output:
35  is divisible by 7 and 5.
```

通过分别对 7 和 5 进行数的模运算，然后检查余数，可以检查一组整数是否可被 7 和 5 除。这可以通过以下方式实现:

## 蟒蛇 3

```py
# enter the starting range number
start_num = int(29)

# enter the ending range number
end_num = int(36)

# initialise counter with starting number
cnt = start_num

# check until end of the range is achieved
while cnt <= end_num:

    # if number divisible by 7 and 5
    if cnt % 7 == 0 and cnt % 5 == 0:
        print(cnt, " is divisible by 7 and 5.")

    # increment counter
    cnt += 1
```

**输出:**

```py
35  is divisible by 7 and 5.
```

这也可以通过检查数字是否能被 35 整除来实现，因为 7 和 5 的 LCM 是 35，任何能被 35 整除的数字也能被 7 和 5 整除，反之亦然。

## 蟒蛇 3

```py
# enter the starting range number
start_num = int(68)

# enter the ending range number
end_num = int(167)

# initialise counter with starting number
cnt = start_num

# check until end of the range is achieved
while cnt <= end_num:

    # check if number is divisible by 7 and 5
    if(cnt % 35 == 0):
        print(cnt, "is divisible by 7 and 5.")

    # incrementing counter
    cnt += 1
```

**输出:**

```py
70 is divisible by 7 and 5.
105 is divisible by 7 and 5.
140 is divisible by 7 and 5.
```