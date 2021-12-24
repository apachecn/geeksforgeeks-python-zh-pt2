# Python–针对给定范围测试列表中的所有偶数元素

> 原文:[https://www . geesforgeks . org/python-给定范围列表中所有偶数元素的测试/](https://www.geeksforgeeks.org/python-test-for-all-even-elements-in-the-list-for-the-given-range/)

给定一个元素列表，测试所有元素是否都在一个范围内。

> **输入** : test_list = [3，1，4，6，8，10，1，9]，I，j = 2，5
> **输出** : True
> **解释** : 4，6，8，10，都是范围内的偶素。
> 
> **输入** : test_list = [3，1，4，6，87，10，1，9]，I，j = 2，5
> **输出** : False
> **解释**:均不在范围内。

**方法#1:使用循环**

在这种情况下，我们迭代指定范围内的列表的一部分，并标记出列表，即使我们发现列表中有任何奇怪的出现。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test for all Even elements in List Range
# Using loop

# initializing list
test_list = [3, 1, 4, 6, 8, 10, 1, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing range 
i, j = 2, 5

res = True 
for idx in range(i, j + 1):

    # check if any odd
    if test_list[idx] % 2 :
        res = False 
        break

# printing result 
print("Are all elements even in range : " + str(res))
```

**Output**

```py
The original list is : [3, 1, 4, 6, 8, 10, 1, 9]
Are all elements even in range : True

```

**方法 2:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，将使用 all()检查所有要平衡的元素，并使用列表理解来循环该范围内的元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test for all Even elements in List Range
# Using all() + list comprehension

# initializing list
test_list = [3, 1, 4, 6, 8, 10, 1, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing range 
i, j = 2, 5

# all() checks for all even elements 
res = all(test_list[idx] % 2 == 0 for idx in range(i, j + 1))

# printing result 
print("Are all elements even in range : " + str(res))
```

**Output**

```py
The original list is : [3, 1, 4, 6, 8, 10, 1, 9]
Are all elements even in range : True

```