# Python 程序，从列表中打印峰或谷的计数

> 原文:[https://www . geeksforgeeks . org/python-从列表中打印峰或谷计数的程序/](https://www.geeksforgeeks.org/python-program-that-prints-the-count-of-either-peaks-or-valleys-from-a-list/)

给定一个列表，下面的文章展示了计算峰(x > y < z) or valley(x < y > z)元素的方法。

> **输入** : test_list = [1，2，4，2，6，7，8，3]
> **输出** : 3
> **解释** : (2，4，2)，(4，2，6)，(7，8，3)为峰谷。
> **输入** : test_list = [1，2，4，5，3，2]
> **输出** : 1
> **解释** : (4，5，3)为峰值。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们对每个元素进行迭代，并检查它的下一个和上一个元素是小于还是大于当前元素。如果找到，计数器将递增。

## 蟒蛇 3

```py
# initializing list
test_list = [1, 2, 4, 2, 6, 7, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

res = 0
for idx in range(1, len(test_list) - 1):
    if test_list[idx + 1] > test_list[idx] < test_list[idx - 1] or test_list[idx + 1] < test_list[idx] > test_list[idx - 1]:
        res += 1

# printing result
print("Peaks and Valleys count : " + str(res))
```

**输出:**

> 原来的名单是:[1，2，4，2，6，7，8，3]
> 
> 峰值和谷值:3

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/)

在本例中，我们使用列表理解来执行获取峰值和谷值的任务，然后使用 len()来计算精确的计数。

## 蟒蛇 3

```py
# initializing list
test_list = [1, 2, 4, 2, 6, 7, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

# one-liner alternative
res = len([test_list[idx] for idx in range(1, len(test_list) - 1) if test_list[idx + 1] >
           test_list[idx] < test_list[idx - 1] or test_list[idx + 1] < test_list[idx] > test_list[idx - 1]])

# printing result
print("Peaks and Valleys count : " + str(res))
```

**输出:**

> 原来的名单是:[1，2，4，2，6，7，8，3]
> 
> 峰值和谷值:3