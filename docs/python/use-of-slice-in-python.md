# Python 中切片()的使用

> 原文:[https://www.geeksforgeeks.org/use-of-slice-in-python/](https://www.geeksforgeeks.org/use-of-slice-in-python/)

有时，代码会变成一堆难以阅读的硬编码切片索引。考虑以下代码，将学生的详细信息(姓名、电话号码、地址、5 科成绩)存储在[列表](https://www.geeksforgeeks.org/python-list/)中，逐一显示，最后显示平均总成绩。

## 蟒蛇 3

```
L = [('Student A', 9876543210, 'Address of A', 99, 82, 97, 78, 69),
     ('Student B', 9999999999, 'Address of B', 90, 83, 87, 72, 67),
     ('Student C', 8888888888, 'Address of C', 88, 41, 56, 61, 93)]

# Display (name, address, phone no., avg marks) for each student
for student in L:
    print(student[0:3], "Marks:", sum(student[3:])/5)

# Average total marks of the class
sum_of_marks = 0
for student in L:
    sum_of_marks += sum(student[3:])

print(sum_of_marks / 3)
```

**输出:**

```
('Student A', 9876543210, 'Address of A') Marks: 85.0
('Student B', 9999999999, 'Address of B') Marks: 79.8
('Student C', 8888888888, 'Address of C') Marks: 67.8
387.6666666666667
```

上面的代码完成了它的工作，但是这个代码可能出现的一个问题是，如果将来我们决定在索引 1 处添加一个条目“Roll no”。那么整个代码都需要修改。另外，这段代码的可读性也不是很好。这只是一个小例子。在大型项目中，我们编写数千行代码。因此，编写可读且可维护的代码成为我们的职责。
通过使用**切片()**构造函数命名切片，可以在一定程度上使相同的代码可读和可维护。

> **语法:**
> 
> *   切片(停止)
>     
> *   切片(开始、停止、步骤)
>     
> 
> **参数:**
> **开始:**对象切片开始的起始索引。
> **停止:**对象切片停止的结束索引。
> **步骤:**它是一个可选的参数，用于确定切片的每个索引之间的增量。
> **返回类型:**返回仅包含给定范围内元素的切片对象。

**注:**切片(1，5，2)对应 a[1:5:2]，切片(1，4)对应 a[1:4]。
让我们重写代码。

## 蟒蛇 3

```
l = [('Student A', 9876543210, 'Address of A', 99, 82, 97, 78, 69),
     ('Student B', 9999999999, 'Address of B', 90, 83, 87, 72, 67),
     ('Student C', 8888888888, 'Address of C', 88, 41, 56, 61, 93)]

# Naming slice
details = slice(0, 3)
marks = slice(3, 8)

# display (name, address, phone no., avg marks) for each student
for student in l:
    print(student[details], "MArks:", sum(student[marks])/5)

# display average total marks of the class
sum_of_marks = 0
for student in l:
    sum_of_marks += sum(student[marks])
print(sum_of_marks / 3)
```

**输出:**

```
('Student A', 9876543210, 'Address of A') MArks: 85.0
('Student B', 9999999999, 'Address of B') MArks: 79.8
('Student C', 8888888888, 'Address of C') MArks: 67.8
387.6666666666667
```