# Python 程序从每个数字中减去 K

> 原文:[https://www . geeksforgeeks . org/python-从每个数字中减去 k 的程序/](https://www.geeksforgeeks.org/python-program-to-subtract-k-from-each-digit/)

给定一个列表，任务是编写一个 Python 程序，从每个数字中减去 K，如果元素低于 0，保留 0。

**示例:**

> **输入:** test_list = [2345，8786，2478，8664，3568，28]，K = 4
> 
> **输出:**【1，4342，34，4220，124，4】
> 
> **解释:**在 2345 年，2 减 4 等于-2，因此等于 0。因此只保留 5-4 = 1。从而输出。
> 
> **输入:** test_list = [2345，8786，2478，8664，3568，28]，K = 3
> 
> **输出:**【12，5453，145，5331，235，5】
> 
> **解释:**在 2345 年，2 减 3 等于-1，因此等于 0。因此只保留了 5-3 = 2 和 4-3 = 1。从而输出。

**方法一:使用**[**str()**](https://www.geeksforgeeks.org/python-str-function/)**+–运算符**

在这种情况下，我们将整数转换为字符串，并通过将每个数字转换为整数来执行减法，结果再次连接，并将类型转换回整数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Subtract K from each digit
# Using str() and - operator

# initializing list
test_list = [2345, 8786, 2478, 8664, 3568, 28]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

res = []
for ele in test_list:
    str_ele = str(ele)

    # getting maximum of 0 or negative value using max()
    # conversion of each digit to int
    new_ele = int(''.join([ str(max(0, int(el) - K)) for el in str_ele]))
    res.append(new_ele)

# printing result
print("Elements after subtracting K from each digit : " + str(res))
```

**输出:**

> 原列表为:[2345，8786，2478，8664，3568，28]
> 
> 每个数字减去 K 后的元素:[1，4342，34，4220，124，4]

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

与上述方法类似，只是列表理解用于提供速记的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Subtract K from each digit
# Using list comprehension

# initializing list
test_list = [2345, 8786, 2478, 8664, 3568, 28]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# list comprehension providing shorthand
res = [int(''.join([ str(max(0, int(el) - K)) for el in str(ele)]))
       for ele in test_list]

# printing result
print("Elements after subtracting K from each digit : " + str(res))
```

**输出:**

> 原列表为:[2345，8786，2478，8664，3568，28]
> 
> 每个数字减去 K 后的元素:[1，4342，34，4220，124，4]