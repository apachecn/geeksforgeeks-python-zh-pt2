# Python–打印列表值字典

> 原文:[https://www . geesforgeks . org/python-print-dictionary-list-values/](https://www.geeksforgeeks.org/python-print-dictionary-of-list-values/)

在本文中，我们将打印一个列表值字典。值列表字典意味着字典包含作为字典列表的值

**示例:**

> {'key1': [{'key1 ':值，……，' key n ':值}……]..{'key1 ':值，……，' key n ':值}}]，
> 
> ————————
> 
> ————————
> 
> keynn:“[{ ' key 1 ':value，……，' key n': value}……”..{'key1 ':值，…，' key n ':值}}]}

所以我们必须根据关键字将字典列在列表中。我们可以通过使用 [dict.items()](https://www.geeksforgeeks.org/python-dictionary-items-method/) 得到这个。

**语法**:

```
d.items()
```

我们可以使用 for 循环遍历字典

```
for key,values in data.items():
     for i in values:
          print(key," : ",i)
```

**示例 1:** Python 代码，用于创建以学生姓名为关键字、值为主题详细信息的字典

## 蟒蛇 3

```
# create a dictionary
# with student names as key
# values as subject details
data = {'manoja': [{'subject1': "java", 'marks': 98}, 
                   {'subject2': "PHP", 'marks': 89}],
        'manoj': [{'subject1': "java", 'marks': 78}, 
                  {'subject2': "PHP", 'marks': 79}]}

# get the list of data
# using items() method
for key, values in data.items():
    for i in values:
        print(key, " : ", i)
```

**输出**:

```
manoja  :  {'subject1': 'java', 'marks': 98}
manoja  :  {'subject2': 'PHP', 'marks': 89}
manoj  :  {'subject1': 'java', 'marks': 78}
manoj  :  {'subject2': 'PHP', 'marks': 79}
```

**例 2** :

## 蟒蛇 3

```
# create a dictionary
# with student names as key
# values as subject details
data = {'manoja': [{'subject1': "java", 'marks': 98}, 
                   {'subject2': "PHP", 'marks': 89}],
        'manoj': [{'subject1': "java", 'marks': 78},
                  {'subject2': "PHP", 'marks': 79}],
        'ramya': [{'subject1': "html", 'marks': 78}]}

# get the list of data
# using items() method
for key, values in data.items():
    for i in values:
        print(key, " : ", i)
```

**输出**:

```
manoja  :  {'subject1': 'java', 'marks': 98}
manoja  :  {'subject2': 'PHP', 'marks': 89}
manoj  :  {'subject1': 'java', 'marks': 78}
manoj  :  {'subject2': 'PHP', 'marks': 79}
ramya  :  {'subject1': 'html', 'marks': 78}
```