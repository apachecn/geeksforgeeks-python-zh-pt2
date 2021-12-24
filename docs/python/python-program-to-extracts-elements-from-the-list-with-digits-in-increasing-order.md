# Python 程序，以数字递增的顺序从列表中提取元素

> 原文:[https://www . geesforgeks . org/python-program-to-extracts-从列表中以数字递增的顺序提取元素/](https://www.geeksforgeeks.org/python-program-to-extracts-elements-from-the-list-with-digits-in-increasing-order/)

给定元素列表，提取所有数字按顺序递增的元素。

> **输入**:test _ list =【1234，7373，3643，3527，148，49】
> **输出**:【1234，148，49】
> **解释**:所有元素都有递增数字。
> **输入** : test_list = [12341，7373，3643，3527，1481，491]
> **输出** : []
> **说明**:无元素都是递增数字。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*str()*](https://www.geeksforgeeks.org/python-str-function/#:~:text=The%20str()%20function%20of,string%20version%20of%20the%20object.&text=object%3A%20The%20object%20whose%20string,errors%3A%20Response%20when%20decoding%20fails.)

在这种情况下，我们将每个元素转换为字符串，然后使用循环检查它们的每个数字是否大于前一个数字。

## 蟒蛇 3

```py
# initializing list
test_list = [1234, 7373, 3643, 3527, 148]

# printing original list
print("The original list is : " + str(test_list))

# loop to check for each element
res = []
for ele in test_list:
    flag = True

    for idx in range(len(str(ele)) - 1):

        # checking for each next digit
        if str(ele)[idx + 1] <= str(ele)[idx]:
            flag = False

    if flag:
        res.append(ele)

# printing result 
print("Extracted increasing digits : " + str(res))
```

**输出:**

```py
The original list is : [1234, 7373, 3643, 3527, 148]
Extracted increasing digits : [1234, 148]
```

**方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*列表理解*](https://www.geeksforgeeks.org/comprehensions-in-python/) *和* [*str()*](https://www.geeksforgeeks.org/python-str-function/#:~:text=The%20str()%20function%20of,string%20version%20of%20the%20object.&text=object%3A%20The%20object%20whose%20string,errors%3A%20Response%20when%20decoding%20fails.)*

*在这种情况下，我们通过对每个元素进行排序并将其与原始版本进行比较来测试元素的每个数字是否增加。如果它们相同，该元素将被添加到所需的列表中。*

## *蟒蛇 3*

```py
*# initializing list
test_list = [1234, 7373, 3643, 3527, 148]

# printing original list
print("The original list is : " + str(test_list))

# sorting and comparing for equality
res = [ele for ele in test_list if ''.join(sorted(str(ele))) == str(ele)]

# printing result 
print("Extracted increasing digits : " + str(res))*
```

***输出:***

```py
*The original list is : [1234, 7373, 3643, 3527, 148]
Extracted increasing digits : [1234, 148]*
```