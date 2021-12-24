# 在 Python 中从 For 循环内部递增迭代器的方法

> 原文:[https://www . geesforgeks . org/从 python 循环内部递增迭代器的方法/](https://www.geeksforgeeks.org/ways-to-increment-iterator-from-inside-the-for-loop-in-python/)

[**对于循环**](https://www.geeksforgeeks.org/python-for-loops/) ，一般来说，都是用于顺序遍历的。它属于确定迭代的范畴。明确的迭代意味着重复的次数是预先明确指定的。但是你有没有想过，如果你试图从 for 循环中增加迭代器的值，会发生什么。让我们借助下面的例子来看看。
**例:**

## 蟒蛇 3

```
lis = [1, 2, 3, 4, 5]

for i in range(len(lis)):

    print(lis[i])
    i += 2
```

**输出:**

```
1
2
3
4
5
```

上面的例子展示了 for 循环的这种奇怪行为，因为 Python 中的 for 循环不是约定的 C 风格 for 循环，即 for(I = 0；一

*   **使用 while 循环:**我们不能直接增加/减少 for 循环体内部的迭代值，我们可以为此使用 While 循环。
    **例:**

## 计算机编程语言

```
# Using while loop

lis = [1, 2, 3, 4, 5]
i = 0

while(i < len(lis)):
    print(lis[i], end = " ")

    # Changing the value of
    # i inside the loop will
    # change it's value at the
    # time of checking condition
    i += 2

```

*   **输出:**

```
1 3 5
```

*   **使用另一个变量:**我们可以出于同样的目的使用另一个变量，因为每次迭代后循环变量的值都会被重新初始化。
    **例:**

## 计算机编程语言

```
# Using for loop

lis = [1, 2, 3, 4, 5]

i = 0

for j in range(len(lis)):

    # Terminating condition for i
    if(i >= len(lis)):
        break

    print(lis[i], end = " ")   
    i += 2
```

*   **输出:**

```
1 3 5
```

*   **使用 range 函数:**我们可以使用 Range 函数作为这个函数的第三个参数指定步长。
    **注:**更多信息请参考 [Python 范围()函数。](https://www.geeksforgeeks.org/python-range-function/)
    **例:**

## 蟒蛇 3

```
# Using for loop

lis = [1, 2, 3, 4, 5]

for i in range(0, len(lis), 2):

    print(lis[i], end = " ")   
```

*   **输出:**

```
1 3 5
```