# Python 程序求一个整数列表所有偶数和奇数的和

> 原文:[https://www . geeksforgeeks . org/python-程序查找整数列表中所有偶数和奇数的总和/](https://www.geeksforgeeks.org/python-program-to-find-the-sum-of-all-even-and-odd-digits-of-an-integer-list/)

下面的文章展示了如何给定一个整数列表，我们可以产生它的所有奇数和偶数的总和。

> **输入**:test _ list =【345，893，1948，34，2346】
> **输出** :
> 奇数位和:36
> 偶数位和:40
> **解释** : 3 + 5 + 9 + 3 + 1 + 9 + 3 + 3 = 36，奇数位和。
> **输入**:test _ list =【345，893】
> **输出** :
> 奇数位和:20
> 偶数位和:12
> **解释** : 4 + 8 = 12，偶数求和。

**方法 1 :** 使用[循环、](https://www.geeksforgeeks.org/loops-in-python/)T4】str()和 [int()](https://www.geeksforgeeks.org/python-int-function/#:~:text=string%20%3A%20consists%20of%201's%20and,string%20in%20the%20given%20base.)

在这种情况下，我们首先将每个元素转换为字符串，然后对其每个元素进行迭代，并通过转换为整数来添加到各自的总和中。

## 蟒蛇 3

```py
# initializing list
test_list = [345, 893, 1948, 34, 2346]

# printing original list
print("The original list is : " + str(test_list))

odd_sum = 0
even_sum = 0

for sub in test_list:
    for ele in str(sub):

        # adding in particular summation according to value 
        if int(ele) % 2 == 0:
            even_sum += int(ele)
        else:
            odd_sum += int(ele)

# printing result 
print("Odd digit sum : " + str(odd_sum))
print("Even digit sum : " + str(even_sum))
```

**输出:**

> 最初的名单是:[345，893，1948，34，2346]
> 
> 奇数和:36
> 
> 偶数和:40

**方法 2 :** 使用循环和[求和()](https://www.geeksforgeeks.org/sum-function-python/)

在本例中，我们使用 sum()执行获取求和的任务，循环用于执行遍历每个元素的任务。

## 蟒蛇 3

```py
# initializing list
test_list = [345, 893, 1948, 34, 2346]

# printing original list
print("The original list is : " + str(test_list))

odd_sum = 0
even_sum = 0

for sub in test_list:

    # sum() used to get summation of even and odd elements
    odd_sum += sum([int(ele) for ele in str(sub) if int(ele) % 2 == 1])
    even_sum += sum([int(ele) for ele in str(sub) if int(ele) % 2 == 0])

# printing result 
print("Odd digit sum : " + str(odd_sum))
print("Even digit sum : " + str(even_sum))
```

**输出:**

> 最初的名单是:[345，893，1948，34，2346]
> 
> 奇数和:36
> 
> 偶数和:40