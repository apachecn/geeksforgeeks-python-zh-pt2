# Python 集|更新()

> 原文:[https://www.geeksforgeeks.org/python-set-update/](https://www.geeksforgeeks.org/python-set-update/)

**集合中的 Python update()函数**将集合中的元素(作为参数传递)添加到集合中。

> **语法:** set1.update(set2)
> 
> 这里 set1 是 set2 将被添加到的集合。
> 
> **参数:** Update()方法只接受一个参数。单个参数可以是集合、列表、元组或字典。它会自动转换成集合并添加到集合中。
> 
> **返回值:**此方法将 set2 添加到 set1，不返回任何内容。

## Python 集更新示例()

### 示例 1:使用 Python 集更新列表

## 蟒蛇 3

```
# Python program to demonstrate the
# use of update() method

list1 = [1, 2, 3]
list2 = [5, 6, 7]
list3 = [10, 11, 12]

# Lists converted to sets
set1 = set(list2)
set2 = set(list1)

# Update method
set1.update(set2)

# Print the updated set
print(set1)

# List is passed as an parameter which
# gets automatically converted to a set
set1.update(list3)
print(set1)
```

**输出:**

```
{1, 2, 3, 5, 6, 7}
{1, 2, 3, 5, 6, 7, 10, 11, 12}
```

### 示例 2: Python 集合中的集合更新元素

## 蟒蛇 3

```
# Python program to demonstrate the
# use of update() method

list1 = [1, 2, 3, 4]
list2 = [1, 4, 2, 3, 5]
alphabet_set = {'a', 'b', 'c'}

# lists converted to sets
set1 = set(list2)
set2 = set(list1)

# Update method
set1.update(set2)

# Print the updated set
print(set1)

set1.update(alphabet_set)
print(set1)
```

**输出:**

```
{1, 2, 3, 4, 5}
{1, 2, 3, 4, 5, 'c', 'b', 'a'}
```

### 示例 3:向集合添加字典元素

## 蟒蛇 3

```
number = {1, 2, 3, 4, 5}

num_Dict = {6: 'Six', 7: 'Seven', 8: 'Eight',
            9: 'Nine', 10: 'Ten'}

number.update(num_Dict)

print("Updated set: ", number)
```

**输出:**

```
Updated set:  {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
```