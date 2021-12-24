# Python |列表中记录元素平均值

> 原文:[https://www . geesforgeks . org/python-record-elements-average-in-list/](https://www.geeksforgeeks.org/python-record-elements-average-in-list/)

给定一个元组列表，编写一个程序，找出列表中相似元组的平均值。

**示例**

```
Input:
[('Geeks', 10), ('For', 10), ('Geeks', 2), ('For', 9), ('Geeks', 10)]

Output:
Resultant list of tuples: [('For', 9.5), ('Geeks', 7.333333333333333)]

Input:
[('Akshat', 10), ('Garg', 10), ('Akshat', 2), ('Garg', 9), ('Akshat', 10)]

Output:
Resultant list of tuples: [('Akshat', 7.333333333333333), ('Garg', 9.5)]

```

**方法一:使用列表理解**

```
# Python code to demonstrate
# find average of similar tuples in list

# initialising list of tuples
ini_list = [('Akshat', 10), ('Garg', 10), ('Akshat', 2),
                            ('Garg', 9), ('Akshat', 10)]

# finding average of similar entries
def avg(l):
    return sum(l)/len(l)

result = [(n, avg([v[1] for v in ini_list
                if v[0] is n])) for n in set([n[0] for n in ini_list])]

# printing result
print ("Resultant list of tuples: {}".format(result))
```

**输出:**

```
Resultant list of tuples: [('Akshat', 7.333333333333333), ('Garg', 9.5)]

```

**方法 2:转换成字典**

```
# Python code to demonstrate
# find average of similar tuples in list

# initialising list of tuples
ini_list = [('Akshat', 10), ('Garg', 10), ('Akshat', 2), 
                            ('Garg', 9), ('Akshat', 10)]

# finding average of similar entries
temp_dict = dict()

for tuple in ini_list:
    key, val = tuple
    temp_dict.setdefault(key, []).append(val)

result = []
for name, values in temp_dict.items():
    result.append((name, (sum(values)/len(values))))

# printing result
print("Resultant list of tuples: {}".format(result))
```

**输出:**

```
Resultant list of tuples: [('Garg', 9.5), ('Akshat', 7.333333333333333)]

```