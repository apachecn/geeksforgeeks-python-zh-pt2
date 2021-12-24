# 在 python 中使用 else 条件语句和 for 循环

> 原文:[https://www . geesforgeks . org/using-else-conditional-statement-with-for-loop-in-python/](https://www.geeksforgeeks.org/using-else-conditional-statement-with-for-loop-in-python/)

在大多数编程语言(C/C++、Java 等)中，else 语句的使用受到 if 条件语句的限制。但是 Python 也允许我们对循环使用 else 条件。

> 仅当循环没有被 break 语句终止时，才会执行 for/while 之后的 else 块。

**Else 块在下面的 Python 3.x 程序中执行:**

## 计算机编程语言

```py
for i in range(1, 4):
    print(i)
else:  # Executed because no break in for
    print("No Break")
```

**输出:**

```py
1
2
3
No Break
```

**否则块不会在下面的 Python 3.x 程序中执行:**

## 计算机编程语言

```py
for i in range(1, 4):
    print(i)
    break
else: # Not executed as there is a break
    print("No Break")
```

**输出:**

```py
1
```

这种类型的 else 只有在循环内部存在某种依赖于循环变量的 if 条件时才有用。
在下面的例子中，else 语句只有在数组中没有元素是偶数的情况下才会被执行，也就是说，如果语句没有被执行过任何迭代。因此，对于数组[1，9，8]，if 在循环的第三次迭代中执行，因此 for 循环之后出现的 else 被忽略。在数组[1，3，5]的情况下，if 不会在任何迭代中执行，因此在循环执行后会执行 else。

## 计算机编程语言

```py
# Python 3.x program to check if an array consists
# of even number
def contains_even_number(l):
    for ele in l:
        if ele % 2 == 0:
            print ("list contains an even number")
            break

    # This else executes only if break is NEVER
    # reached and loop terminated after all iterations.
    else:    
        print ("list does not contain an even number")

# Driver code
print ("For List 1:")
contains_even_number([1, 9, 8])
print (" \nFor List 2:")
contains_even_number([1, 3, 5])
```

**输出:**

```py
For List 1:
list contains an even number

For List 2:
list does not contain an even number
```

作为**练习**，预测以下程序的输出。

## 计算机编程语言

```py
count = 0
while (count < 1):   
    count = count+1
    print(count)
    break
else:
    print("No Break")
```

本文由 **Harshit Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。