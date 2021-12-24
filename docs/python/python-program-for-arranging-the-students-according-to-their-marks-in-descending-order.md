# 按照分数降序排列学生的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-按分数降序排列学生的程序/](https://www.geeksforgeeks.org/python-program-for-arranging-the-students-according-to-their-marks-in-descending-order/)

考虑一个有 20 名学生的班级，他们的名字和分数都给了你。任务是按照分数降序排列学生。编写一个 python 程序来执行任务。

**示例:**

```py
Input:
Arun: 78%
Geeta: 86%
Shilpi: 65%

Output: 
Geeta: 86%
Arun: 78%
Shilpi: 65%

```

**方法:**由于问题说明我们需要先收集学生姓名和他们的分数，因此为此，我们将在列表数据结构中逐个输入，然后使用基于学生百分比的 sorted()内置函数以相反的顺序对其进行排序，最后我们将相应地打印该值。

下面是实现:

## 蟒蛇 3

```py
print("-----Program for printing student name with marks using list-----")

# create an empty dictionary
D = {}

n = int(input('How many student record you want to store?? '))

# create an empty list
# Add student information to the list
ls = []

for i in range(0, n):

      # Take combined input name and 
    # percentage and split values 
    # using split function.
    x,y = input("Enter the student name and it's percentage: ").split()

    # Add name and marks stored in x, y
    # respectively using tuple to the list
    ls.append((y,x))

# sort the elements of list
# based on marks
ls = sorted(ls, reverse = True)

print('Sorted list of students according to their marks in descending order')

for i in ls:

    # print name and marks stored in 
    # second and first position 
    # respectively in list of tuples.
    print(i[1], i[0])
```

**输出:**

```py
-----Program for printing student name with marks using list-----
How many student record you want to store?? 3
Enter the student name and percentage: Arun: 78%
Enter the student name and percentage: Geeta: 86%
Enter the student name and percentage: Shilpi: 65%
Sorted list of students according to their marks in descending order
Geeta: 86%
Arun: 78%
Shilpi: 65%

```