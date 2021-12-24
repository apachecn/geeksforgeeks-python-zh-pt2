# Python 集–交集 _ 更新()函数

> 原文:[https://www . geesforgeks . org/python-set-intersection _ update-function/](https://www.geeksforgeeks.org/python-set-intersection_update-function/)

**Python 交集 _update()函数**用于获取所有给定集合中存在的元素。它将删除所有集合中不存在的元素。

**语法:**

```py
set.intersection_update(set1,set2,set3,...........,set n)
```

其中，set1、set2 是输入集。它可以采取任何数量的集合。

**注意:**要执行此功能，我们至少有两套。

**示例:** Python 程序用字符串元素定义两个集合。

## 蟒蛇 3

```py
# declare set1
set1 = {"java", "python", "c/cpp", "html"}

# declare set2
set2 = {"php", "html", "java", "R"}

# display sets
print(set1, set2)

# perform intersection_update operation 
# on both the sets
set.intersection_update(set1, set2)

# display the result set
print(set1)
```

**输出:**

> {'c/cpp '，' python '，' html '，' java'} {'php '，' r '，' html '，' java'}
> 
> {“html”、“Java”}

**示例 2** :多个集合上的交集 _ 更新操作。

## 蟒蛇 3

```py
# declare set1
set1 = {"java", "python", "c/cpp", "html"}

# declare set2
set2 = {"php", "html", "java", "R"}

# declare set3
set3 = {"java", "python", "ml", "dl"}

# declare set4
set4 = {"python", "java", "swift", "R"}

# display sets
print(set1, set2, set3, set4)

# perform intersection_update operation on
# all the sets
set.intersection_update(set1, set2, set3, set4)

# display the result set
print(set1)
```

**输出:**

> {'java '，' html '，' c/cpp '，' python'} {'java '，' php '，' html '，' R'} {'java '，' ml '，' dl '，' python'} {'python '，' java '，' swift '，' r '
> 
> {“Java”}

**例 3:**

这里我们创建了两个集合，这两个集合中没有公共元素，所以输出应该是空的。在所有集合中，没有共同的元素，因此输出是一个空集合。

## 蟒蛇 3

```py
# declare set1
set1 = {"java", "python", "c/cpp", "html"}

# declare set2
set2 = {"php", "cn", "dbms", "R"}

# display sets
print(set1, set2)

# perform intersection_update operation on 
# both the sets
set.intersection_update(set1, set2)

# display the result set
print(set1)
```

**输出:**

> {'java '，' python '，' c/cpp '，' html'} {'R '，' cn '，' dbms '，' php '
> 
> 设置()