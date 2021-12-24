# Python |选择性记录值求和

> 原文:[https://www . geesforgeks . org/python-选择性-记录-值-求和/](https://www.geeksforgeeks.org/python-selective-records-value-summation/)

有时，在使用元组列表时，我们会遇到一个问题，即我们有某个键列表，而我们只需要元组列表中这些键的值的总和。这在对特定实体进行评级或汇总时很有用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`dict() + sum() + get()` +列表理解**
我们可以执行这个特定的任务，首先将列表转换成字典，然后使用列表理解使用 get 函数获取特定键的值。使用 sum()执行值的求和。

```
# Python3 code to demonstrate 
# Selective Records Value Summation
# using dict() + get() + list comprehension + sum()

# initializing list of tuples 
test_list = [('Nikhil', 1), ('Akash', 2), ('Akshat', 3), ('Manjeet', 4)]

# initializing selection list 
select_list = ['Nikhil', 'Akshat']

# printing original list 
print ("The original list is : " + str(test_list))

# printing selection list 
print ("The selection list is : " + str(select_list))

# using dict() + get() + list comprehension + sum()
# Selective Records Value Summation
temp = dict(test_list)
res = sum([temp.get(i, 0) for i in select_list])

# printing result
print ("The selective values summation of keys : " + str(res))
```

**Output :**

```
The original list is : [('Nikhil', 1), ('Akash', 2), ('Akshat', 3), ('Manjeet', 4)]
The selection list is : ['Nikhil', 'Akshat']
The selective values summation of keys : 4

```