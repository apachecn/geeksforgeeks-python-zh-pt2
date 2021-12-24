# Python 程序反转列表中的范围

> 原文:[https://www . geesforgeks . org/python-program-to-reverse-a-range in-list/](https://www.geeksforgeeks.org/python-program-to-reverse-a-range-in-list/)

给定一个列表，我们的任务是编写一个 Python 程序来反转列表中的一个范围。

**示例:**

> **输入:** test_list = [6，3，1，8，9，2，10，12，7，4，11]，str，end = 3，9
> 
> **输出:**【6、3、1、7、12、10、2、9、8、4、11】
> 
> **说明:**列表中 8、9、2、10、12、7 颠倒为 7、12、10、2、9、8。
> 
> **输入:** test_list = [6，3，1，8，9，2，10，12，7，4，11]，str，end = 8，9
> 
> **输出:**【6、3、1、8、9、2、10、7、12、4、11】
> 
> **说明:** 12，7 在列表中反转为 7，12。

**方法#1:使用** [**反向()**](https://www.geeksforgeeks.org/python-list-reverse/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在本例中，使用 reverse()提取并反转子列表。循环接下来用于将范围元素替换为反向元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Reversing a range
# Using reverse() + loop

# initializing list
test_list = [6, 3, 1, 8, 9, 2, 10, 12, 7, 4, 11]

# printing original list
print("The original list is : " + str(test_list))

# initializing range 
strt, end = 3, 9

# reversing list and assigning the range
temp = test_list[strt:end]
temp.reverse()
for idx in range(strt, end):
    test_list[idx] = temp[idx - strt]

# printing result
print("Range reversed range list : " + str(test_list))
```

**输出:**

```
The original list is : [6, 3, 1, 8, 9, 2, 10, 12, 7, 4, 11]
Range reversed range list : [6, 3, 1, 7, 12, 10, 2, 9, 8, 4, 11]
```

**方法 2:使用列表** [**分割()**](https://www.geeksforgeeks.org/python-string-split/) **+** [**切片**](https://www.geeksforgeeks.org/string-slicing-in-python/)

解决这个问题的紧凑方法是使用列表分割方式执行范围列表的反转，这种方式只反转切片所需的范围。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Reversing a range
# Using list split + slicing

# initializing list
test_list = [6, 3, 1, 8, 9, 2, 10, 12, 7, 4, 11]

# printing original list
print("The original list is : " + str(test_list))

# initializing range 
strt, end = 3, 9

# Third arg. of split with -1 performs reverse 
test_list[strt:end] = test_list[strt:end][::-1]

# printing result
print("Range reversed range list : " + str(test_list))
```

**输出:**

```
The original list is : [6, 3, 1, 8, 9, 2, 10, 12, 7, 4, 11]
Range reversed range list : [6, 3, 1, 7, 12, 10, 2, 9, 8, 4, 11]
```