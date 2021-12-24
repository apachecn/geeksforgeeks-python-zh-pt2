# Python 程序，用于测试列表中的 x 之后是否出现所有 y

> 原文:[https://www . geeksforgeeks . org/python-程序到测试-如果所有 y 都发生在列表中的 x 之后/](https://www.geeksforgeeks.org/python-program-to-test-if-all-y-occur-after-x-in-list/)

给定一个列表，测试 y 的所有出现是否都在列表中 x 的出现之后。

> **输入** : test_list = [4，5，6，2，4，5，2，9]，x，y = 6，2
> **输出** : True
> **解释**:2 的所有出现都在 6 之后，因此为 True。
> 
> **输入** : test_list = [4，2，5，6，2，4，5，2，9]，x，y = 6，2
> **输出** : False
> **解释**:2 的所有出现都不是在 6 之后，因此为 true。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**索引()**](https://www.geeksforgeeks.org/python-list-index/#:~:text=index()%20is%20an%20inbuilt,index%20where%20the%20element%20appears.&text=Parameters%20%3A,lowest%20index%20will%20be%20returned.)

在这种情况下，我们在列表中检查 x 的索引，然后运行一个循环来获得 y 的出现，如果任何 y 出现在 x 索引之前，结果是 False。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if y occurs after x in List
# Using loop + index()

# initializing list
test_list = [4, 5, 6, 2, 4, 5, 2, 9]

# printing original lists
print("The original list is : " + str(test_list))

# initializing x, y 
x, y = 6, 2

# getting index of x 
xidx = test_list.index(x)

res = True 
for idx, ele in enumerate(test_list):

    # checking for y and comparing index 
    if ele == y and idx < xidx:
        res = False 
        break

# printing result 
print("Do all y occur after x : " + str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 2, 4, 5, 2, 9]
Do all y occur after x : True
```

**方法 2:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+index()**

在本例中，我们使用 all()测试 y 的所有索引，index()用于获取列表中 x 的索引。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if y occurs after x in List
# Using all() + index()

# initializing list
test_list = [4, 5, 6, 2, 4, 5, 2, 9]

# printing original lists
print("The original list is : " + str(test_list))

# initializing x, y 
x, y = 6, 2

# getting index of x 
xidx = test_list.index(x)

# checking for all indices of y in list 
res = all(idx > xidx for idx, ele in enumerate(test_list) if ele == y)

# printing result 
print("Do all y occur after x : " + str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 2, 4, 5, 2, 9]
Do all y occur after x : True
```