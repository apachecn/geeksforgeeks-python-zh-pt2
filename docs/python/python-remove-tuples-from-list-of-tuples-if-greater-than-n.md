# Python |从元组列表中删除大于 n 的元组

> 原文:[https://www . geesforgeks . org/python-从元组列表中移除元组-如果大于-n/](https://www.geeksforgeeks.org/python-remove-tuples-from-list-of-tuples-if-greater-than-n/)

给定一个元组列表，任务是从列表中移除所有元组，如果它大于 *n* (比如 100)。让我们讨论几个相同的方法。

**方法#1:使用λ**

```
# Python code to demonstrate
# to remove the tuples
# if certain criteria met

# initialising _list
ini_tuple = [('b', 100), ('c', 200), ('c', 45),
                         ('d', 876), ('e', 75)]

# printing iniial_tuplelist
print("intial_list", str(ini_tuple))

# removing tuples for condition met
result = [i for i in ini_tuple if i[1] <= 100]

# printing resultant tuple list
print ("Resultant tuple list: ", str(result))

```

**输出:**

> intial_list [('b '，100)、(' c '，200)、(' c '，45)、(' d '，876)、(' e '，75)]
> 结果元组列表:[('b '，100)、(' c '，45)、(' e '，75)]

**方法 2:使用滤镜+λ**

```
# Python code to demonstrate
# to remove the tuples
# if certain criteria met

# initialising _list
ini_tuple = [('b', 100), ('c', 200), ('c', 45),
                         ('d', 876), ('e', 75)]

# printing iniial_tuplelist
print("intial_list", str(ini_tuple))

# removing tuples for condition met
result = list(filter(lambda x: x[1] <= 100, ini_tuple))

# printing resultant tuple list
print ("Resultant tuple list: ", str(result))
```

**输出:**

> intial_list [('b '，100)、(' c '，200)、(' c '，45)、(' d '，876)、(' e '，75)]
> 结果元组列表:[('b '，100)、(' c '，45)、(' e '，75)]

**方法#3:使用天真方法**

```
# Python code to demonstrate
# to remove the tuples
# if certain criteria met

# initialising _list
ini_tuple = [('b', 100), ('c', 200), ('c', 45), 
                         ('d', 876), ('e', 75)]

# printing iniial_tuplelist
print("intial_list", str(ini_tuple))

# removing tuples for condition met
result = []
for i in ini_tuple:
    if i[1] <= 100:
        result.append(i)

# printing resultant tuple list
print ("Resultant tuple list: ", str(result))

```

**输出:**

> intial_list [('b '，100)、(' c '，200)、(' c '，45)、(' d '，876)、(' e '，75)]
> 结果元组列表:[('b '，100)、(' c '，45)、(' e '，75)]