# 计算生命路径号的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到计算-生命-路径-编号/](https://www.geeksforgeeks.org/python-program-to-compute-life-path-number/)

给定一串格式为 YYYMMDD 的日期，我们的任务是计算生命路径号。**生命路径号**是日期串中每个元素的单个数字重复求和直到一位数得到的数字。用于命理预测。

**示例:**

> **输入:**test _ str =“19970314”
> 
> **输出:** 7
> 
> **说明:** 1 + 9 + 9 + 7 = 26，2 + 6 = 8 [年]；0 + 3 = 3 [月]；1 + 4 = 5 [天]。5 + 3 + 8 = 16 ;1 + 6 = 7.
> 
> **输入:**test _ str =“19970104”
> 
> **输出:** 4
> 
> **说明:** 1 + 9 + 9 + 7 = 26，2 + 6 = 8 [年]；0 + 1 = 1 [月]；0 + 4 = 4 [天]。4 + 1 + 8 = 13 ;1 + 3 = 4.

**方法 1:使用循环**

计算的逻辑是得到每个数字的总和，并在每一步执行%10。这样的话，如果达到两位数，卷发器就会变成个位数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Life Path Number
# Using loop

# initializing string
test_str = "19970314"

# printing original string
print("The original string is : " + str(test_str))

res = 0
for num in test_str:
    res += int(num)

    # modulation in case of 2 digit number
    if res > 9:
        res = res % 10 + res // 10

# printing result
print("Life Path Number  : " + str(res))
```

**输出:**

```
The original string is : 19970314
Life Path Number  : 7
```

**方法二:使用递归**

与上面类似，不同之处在于递归函数用于在数字计数大于 1 的情况下重复调制。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Life Path Number
# Using recursion

# initializing string
test_str = "19970314"

# printing original string
print("The original string is : " + str(test_str))

# recursion function definition
def lpn(num): return num if num < 10 else lpn(num // 10 + num % 10)

# recursive function initial call
res = lpn(int(test_str))

# printing result
print("Life Path Number  : " + str(res))
```

**输出:**

```
The original string is : 19970314
Life Path Number  : 7
```