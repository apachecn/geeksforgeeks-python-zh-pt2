# Python–根据数字对列表项目进行排序

> 原文:[https://www . geesforgeks . org/python-sort-list-items-按数字排序/](https://www.geeksforgeeks.org/python-sort-list-items-on-basis-of-their-digits/)

给定元素列表，根据数字位数进行排序。

> **输入**:test _ list =【434，211，12，3】
> **输出**:【12，211，3，434】
> **解释** : 3 < 12，后面还有列表，作为起始数字，1 < 3。因此按数字而不是数字排序。
> 
> **输入**:test _ list =【534，211，12，7】
> **输出**:【12，211，534，7】
> **解释** : 7 < 534，后面还有列表，作为起始数字，5 < 7。因此按数字而不是数字排序。

**方法#1:使用 map()+str()+ljust()+sorted()**

在这种情况下，使用 map()将列表元素转换为字符串，并使用 str()，ljust()追加常量字符，使每个数字的长度相等。然后使用 sorted()执行排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort List by Digits
# Using map() + str() + ljust() + sorted()

# initializing list
test_list = [434, 211, 12, 54, 3]

# printing original list
print("The original list is : " + str(test_list))

# converting elements to string 
temp1 = map(str, test_list)

# getting max length
max_len = max(map(len, temp1))

# performing sort operation
res = sorted(test_list, key = lambda idx : (str(idx).ljust(max_len, 'a')))

# printing result 
print("List after sorting : " + str(res))
```

**Output**

```
The original list is : [434, 211, 12, 54, 3]
List after sorting : [12, 211, 3, 434, 54]

```

**方法 2:使用列表理解+排序()+ lambda**

在这种情况下，我们作为参数向 sorted()传递一个数字列表。根据给出的期望结果执行排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort List by Digits
# Using list comprehension + sorted() + lambda

# initializing list
test_list = [434, 211, 12, 54, 3]

# printing original list
print("The original list is : " + str(test_list))

# performing sort operation
# converting number to list of Digits
res = sorted(test_list, key = lambda ele: [int(j) for j in str(ele)])

# printing result 
print("List after sorting : " + str(res))
```

**Output**

```
The original list is : [434, 211, 12, 54, 3]
List after sorting : [12, 211, 3, 434, 54]

```