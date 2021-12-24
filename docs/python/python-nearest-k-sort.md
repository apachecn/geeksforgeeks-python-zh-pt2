# Python–最近 K 排序

> 原文:[https://www.geeksforgeeks.org/python-nearest-k-sort/](https://www.geeksforgeeks.org/python-nearest-k-sort/)

给定一个元素列表，根据它与 k 的距离进行排序

> **输入**:test _ list =【6、7、4、11、17、8、3】，K = 10
> **输出**:【11、8、7、6、4、17、3】
> **解释**:11-10 = 1；<10–8 = 2..按差值递增排序。
> 
> **输入**:test _ list =【6，7，4，11】，K = 10
> **输出**:【11，7，6，4】
> **解释**:11-10 = 1；<10–7 = 3..按差值递增排序。

**方法#1:使用 sort() + abs()**

在这种情况下，我们使用 *sort()* 和 *abs()* 来执行排序，用于逻辑形成以执行排序操作。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Nearest K Sort
# Using sort() + abs()

# getting absolute difference
def get_diff(ele):

    # returning absolute difference
    return abs(ele - K)

# initializing list
test_list = [6, 7, 4, 11, 17, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 10

# performing inplace sort using sort()
test_list.sort(key=get_diff)

# printing result
print("Sorted List : " + str(test_list))
```

**Output**

```py
The original list is : [6, 7, 4, 11, 17, 8, 3]
Sorted List : [11, 8, 7, 6, 4, 17, 3]

```

**方法 2:使用排序的()+λ+ABS()**

与上述方法类似，这里 *sorted()* 用于执行排序操作，而不是调用外部函数， *lambda* 用于提供排序逻辑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Nearest K Sort
# Using sorted() + abs() + lambda

# initializing list
test_list = [6, 7, 4, 11, 17, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 10

# sorted() used to perform sorting, lambda function to get logic
res = sorted(test_list, key=lambda ele: abs(ele - K))

# printing result
print("Sorted List : " + str(res))
```

**Output**

```py
The original list is : [6, 7, 4, 11, 17, 8, 3]
Sorted List : [11, 8, 7, 6, 4, 17, 3]

```