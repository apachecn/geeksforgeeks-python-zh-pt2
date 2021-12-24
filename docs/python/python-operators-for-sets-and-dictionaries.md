# 集合和字典的 Python 运算符

> 原文:[https://www . geesforgeks . org/python-集合和字典运算符/](https://www.geeksforgeeks.org/python-operators-for-sets-and-dictionaries/)

以下文章主要讨论[集](https://www.geeksforgeeks.org/sets-in-python/)和[词典](https://www.geeksforgeeks.org/python-dictionary/)中使用的运算符。通过使用各种关键字和符号，运算符有助于将现有值组合成更大的语法表达式。

1.  **集合:**集合类用于表示没有重复的元素集合，并且这些元素没有任何固有的顺序。它由{}括起来，每个元素由逗号(，)分隔，并且是可变的。

**示例:**

## 蟒蛇 3

```
# set of alphabet
set = {'a', 'b', 'c', 'd', 'e'}
print(set)
```

**输出:**

```
{'c', 'b', 'd', 'e', 'a'}

```

2。**frozensents:**它是一个集合的不可改变的形式，用来构成集合的一个集合。

set 和 frozensets 支持以下运算符:

*   s: 中的**键<u>用于检查给定的键是否在设定中。</u>**
*   **键<u>不在</u> s** 中:如果键不在设置中，则返回真。

**示例:**

## 蟒蛇 3

```
s = {4, 5, 8, 6, 3, 2, 5}
key = 3
x = key in s  # containment check
y = key not in s  # non-containment check
print(x, y)
```

**输出:**

```
True False

```

*   **s1 == s2 :** 检查 s1 相当于 s2。即 s1 的所有元素都在 s2 中，反之亦然。如果 s1 等于 s2，则返回真。
*   **s1！= s2 :** s1 不等于 s2。即 s1 的至少一个元素不在 s2 中。如果 s1 不等于 s2，则返回真。

**示例:**

## 蟒蛇 3

```
s1 = {'t', 3, 6, 5, 7, 8, 4, 9}
s2 = {5, 7, 8, 9, 't', 4, 3, 6}

# equivalent check
x = s1 == s2

# non-equivalent check
y = s1 != s2
print(x)
print(y)
```

**输出:**

```
True
False

```

集合的比较不是字典式的，因为集合没有按照正确的顺序排列它们的元素。因此，s1 不能大于或小于 s2，反之亦然，相反，它们可以是子集或超集。

*   **s1 < = s2 :** s1 是 s2 的子集。即 s1 的所有元素都在 s2 中，如果 s1 是 s2 的子集，则返回 True。
*   **s1 < s2 :** s1 是 s2 的适当子集。即 s1 的所有元素都在 s2 中，但 s2 的所有元素不一定都在 s1 中，如果 s1 是 s2 的适当子集，则返回真。
*   **s1 > = s2 :** s1 是 s2 的超集。即 s2 的所有元素都在 s1 中，如果 s1 是 s2 的超集，则返回 True。
*   **s1 > s2 :** s1 是 s2 的适当超集。即 s2 的所有元素都在 s1 中，但 s1 的所有元素不一定都在 s2 中，如果 s1 是 s2 的适当超集，则返回真。

**示例:**

## 蟒蛇 3

```
s1 = {2, 5, 3, 7, 'c', 'a', 8}
s2 = {3, 7, 8, 'c'}

# subset check
w = s1 <= s2

# proper subset check
x = s1 < s2

# superset check
y = s1 >= s2

# proper superset check
z = s1 > s2
print(w, x, y, z)
```

**输出:**

```
False False True True

```

*   **s1 | s2:**S1 和 s2 的并集，不重复返回 S1 和 S2 的元素。
*   **S1&s2:**S1 和 S2 的交集，返回两个集合中存在的元素。
*   **s1 s2:**设置差异，返回在 S1 中但不在 S2 中的元素。
*   **s1 \u s2:**恰好在 s1 或 s2 之一中的元素集合，返回在 s1 中但不在 s2 中的元素和在 S2 中但不在 S1 中的元素。

**示例:**

## 蟒蛇 3

```
s1 = {2, 5, 3, 7, 'c', 'a', 8}
s2 = {3, 7, 8, 'c', 9, 11, 'd'}

# union
w = s1 | s2

# intersection
x = s1 & s2

# elements which are in s1 but not in s2
# and elements which are in s2 but not in s1
y = s1 ^ s2

# set difference
z = s1-s2
print(w)
print(x)
print(y)
print(z)
```

**输出:**

> {2，3，5，a，7，8，9，11，d，c }
> 
> {8，' c '，3，7}
> 
> {2，5，9，' d '，11，' a'}
> 
> {2，5，' a'}

3.**字典:**是不同键到其关联值的映射。我们也使用花括号{ }来创建字典。

**示例:**

## 蟒蛇 3

```
# Example of Dictionary
d = {'jupiter': 'planet', 'sun': 'star'}
print(d)
```

**输出:**

```
{'jupiter': 'planet', 'sun': 'star'}

```

字典支持以下运算符:

*   **d【键】:**用于从字典中获取与给定键关联的值。
*   **d【键】=值**:用于从字典中设置(或重置)与给定键相关的值。
*   **del d[key]:** 用于从字典中删除键及其关联值。

**示例:**

## 蟒蛇 3

```
dict = {'math': 45, 'english': 60, 'science': 65, 
        'computer science': 70}

# retrieving value by using key
x = dict['science']
print(x)

# reassigning value
dict['english'] = 80
print(dict)

# deleting
del dict['math']
print(dict)
```

**输出:**

> 65
> {“数学”:45，“英语”:80，“科学”:65，“计算机科学”:70}
> {“英语”:80，“科学”:65，“计算机科学”:70}

*   **d 中的键:**用于检查字典中是否有某个键。也称为遏制检查。它返回一个布尔值。
*   **键不在 d:** 它返回一个布尔值，如果该键不在字典中，则为 True，也称为非包含检查

**示例:**

## 蟒蛇 3

```
dict = {'math': 45, 'english': 60, 'science': 65,
        'computer science': 70}

# containment check
x = 'english' in dict

# non-containment check
y = 'hindi' not in dict
print(x)
print(y)
```

**输出:**

```
True
True

```

*   **d1 == d2:** 它比较两个字典的键值对，如果找到，返回 True。
*   **d1！= d2:** 它比较两个字典的键值对，如果找到则返回 True。

**示例:**

## 蟒蛇 3

```
d1 = {'a': 5, 'b': 7, 'c': 9, 'e': 3}
d2 = {'c': 9, 'a': 5, 'b': 7, 'e': 3}

x = d1 == d2
y = d1 != d2

print(x)
print(y)
```

**输出:**

```
True
False

```

字典类似于集合。它们也没有任何明确顺序的元素。

子集和超集的概念不适用于词典。因此，子集和超集运算符对它来说毫无意义。