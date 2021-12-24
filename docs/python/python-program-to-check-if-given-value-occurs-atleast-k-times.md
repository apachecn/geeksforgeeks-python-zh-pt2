# Python 程序检查给定值是否至少出现 k 次

> 原文:[https://www . geesforgeks . org/python-程序检查给定值是否发生-至少-k 次/](https://www.geeksforgeeks.org/python-program-to-check-if-given-value-occurs-atleast-k-times/)

给定一个列表和一些值(假设它是 N)，编写一个 Python 程序来检查给定的值是否在该列表中出现了至少 k 次。

我们可以用列表理解来处理这个问题。我们可以添加给定值的每次出现，并检查它是否大于或等于 k。如果返回的值为真，则将标志设置为 1，否则为 0。

下面是 Python 实现–

```py
# Python program to check if given
# value occurs atleast k times

test_list = [1, 3, 5, 5, 4, 5] 

# printing original list 
print ("The original list is : " + str(test_list)) 

# value to be checked  
val = 5

# initializing k 
k = 3

# using sum() + list comprehension 
# checking occurrences
res = 0
res = sum([1 for i in test_list if i == val]) >= k

if res == 1 : res = True
else :  res = False

# printing result  
print ("%d occur atleast %d times ? :" %(val, k) + str(res)) 
```

**输出:**

```py
The original list is : [1, 3, 5, 5, 4, 5]
5 occur atleast 3 times ? :True

```