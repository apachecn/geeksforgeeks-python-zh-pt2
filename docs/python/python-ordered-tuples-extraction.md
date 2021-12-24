# Python–有序元组提取

> 原文:[https://www . geesforgeks . org/python-ordered-元组-抽取/](https://www.geeksforgeeks.org/python-ordered-tuples-extraction/)

给定一个元组列表，获取所有按升序排序的元组。

> **输入** : test_list = [(5，4，6，2，4)，(3，4，6)，(2，5，6)，(9，1)]
> **输出** : [(3，4，6)，(2，5，6)]
> **:提取排序后的元组。**
> 
> ****输入** : test_list = [(5，4，6，2，4)，(3，4，1)，(2，5，4)，(9，1)]
> **输出** : []
> **解释**:无排序元组。**

****方法#1:使用列表理解+排序()****

**在本文中，我们使用 sorted()检查元组是否有序，并使用列表理解来迭代每个元组。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of 
# Ordered tuples extraction
# Using list comprehension + sorted()

# initializing list
test_list = [(5, 4, 6, 2, 4), (3, 4, 6), (9, 10, 34), (2, 5, 6), (9, 1)]

# printing original list
print("The original list is : " + str(test_list))

# sorted() used to order, comparison operator to test 
res = [sub for sub in test_list if tuple(sorted(sub)) == sub]

# printing result 
print("Ordered Tuples : " + str(res))
```

****Output**

```
The original list is : [(5, 4, 6, 2, 4), (3, 4, 6), (9, 10, 34), (2, 5, 6), (9, 1)]
Ordered Tuples : [(3, 4, 6), (9, 10, 34), (2, 5, 6)]

```** 

****方法 2:使用 filter() + lambda + sorted()****

**在这种情况下，过滤任务是使用 filter()完成的，sorted()被馈送到 lambda 进行比较，以获得所需的结果。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of 
# Ordered tuples extraction
# Using filter() + lambda + sorted()

# initializing list
test_list = [(5, 4, 6, 2, 4), (3, 4, 6), (9, 10, 34), (2, 5, 6), (9, 1)]

# printing original list
print("The original list is : " + str(test_list))

# sorted() used to order, comparison operator to test 
res = list(filter(lambda sub: tuple(sorted(sub)) == sub, test_list))

# printing result 
print("Ordered Tuples : " + str(res))
```

****Output**

```
The original list is : [(5, 4, 6, 2, 4), (3, 4, 6), (9, 10, 34), (2, 5, 6), (9, 1)]
Ordered Tuples : [(3, 4, 6), (9, 10, 34), (2, 5, 6)]

```**