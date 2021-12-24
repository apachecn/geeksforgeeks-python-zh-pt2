# Python 中的 zip()

> 原文:[https://www.geeksforgeeks.org/zip-in-python/](https://www.geeksforgeeks.org/zip-in-python/)

**Python zip()方法**获取可迭代或容器，并返回一个迭代器对象，该对象已经映射了所有容器的值。

用于映射多个容器的相似索引，使其仅使用单个实体即可使用。

> **语法:**zip(*迭代器)
> 
> **参数:** Python iterables 或容器(列表、字符串等)
> **返回值:**返回单个迭代器对象，已映射所有
> 容器的值。

## Python zip()示例

### 示例 1: Python 压缩两个列表

## 蟒蛇 3

```
name = [ "Manjeet", "Nikhil", "Shambhavi", "Astha" ]
roll_no = [ 4, 1, 3, 2 ]

# using zip() to map values
mapped = zip(name, roll_no)

print(set(mapped))
```

**输出:**

```
{('Shambhavi', 3), ('Nikhil', 1), ('Astha', 2), ('Manjeet', 4)}
```

### 示例 2: Python zip **枚举**

## 蟒蛇 3

```
names = ['Mukesh', 'Roni', 'Chari']
ages = [24, 50, 18]

for i, (name, age) in enumerate(zip(names, ages)):
    print(i, name, age)
```

**输出:**

```
0 Mukesh 24
1 Roni 50
2 Chari 18
```

### 示例 3: Python zip()字典

## 蟒蛇 3

```
stocks = ['reliance', 'infosys', 'tcs']
prices = [2175, 1127, 2750]

new_dict = {stocks: prices for stocks,
            prices in zip(stocks, prices)}
print(new_dict)
```

**输出:**

```
{'reliance': 2175, 'infosys': 1127, 'tcs': 2750}
```

## **如何解压？**

解压缩意味着将压缩后的值转换回原来的个人。这是在“ ***** ”操作符的帮助下完成的。

## 蟒蛇 3

```
# Python code to demonstrate the working of
# unzip

# initializing lists
name = ["Manjeet", "Nikhil", "Shambhavi", "Astha"]
roll_no = [4, 1, 3, 2]
marks = [40, 50, 60, 70]

# using zip() to map values
mapped = zip(name, roll_no, marks)

# converting values to print as list
mapped = list(mapped)

# printing resultant values
print("The zipped result is : ", end="")
print(mapped)

print("\n")

# unzipping values
namz, roll_noz, marksz = zip(*mapped)

print("The unzipped result: \n", end="")

# printing initial lists
print("The name list is : ", end="")
print(namz)

print("The roll_no list is : ", end="")
print(roll_noz)

print("The marks list is : ", end="")
print(marksz)
```

**输出:**

```
The zipped result is : [('Manjeet', 4, 40), ('Nikhil', 1, 50), 
('Shambhavi', 3, 60), ('Astha', 2, 70)]

The unzipped result: 
The name list is : ('Manjeet', 'Nikhil', 'Shambhavi', 'Astha')
The roll_no list is : (4, 1, 3, 2)
The marks list is : (40, 50, 60, 70)
```

## **实际应用**

有许多可能的应用程序可以说是使用 zip 执行的，无论是**学生数据库还是记分卡**或者任何其他需要组映射的实用程序。下面展示了记分卡的一个小例子。

## 蟒蛇 3

```
# Python code to demonstrate the application of
# zip()

# initializing list of players.
players = ["Sachin", "Sehwag", "Gambhir", "Dravid", "Raina"]

# initializing their scores
scores = [100, 15, 17, 28, 43]

# printing players and scores.
for pl, sc in zip(players, scores):
    print("Player :  %s     Score : %d" % (pl, sc))
```

**输出:**

```
Player :  Sachin     Score : 100
Player :  Sehwag     Score : 15
Player :  Gambhir     Score : 17
Player :  Dravid     Score : 28
Player :  Raina     Score : 43
```