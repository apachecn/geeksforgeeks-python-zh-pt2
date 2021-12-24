# Python 程序对学生记录中的数据进行排序和查找

> 原文:[https://www . geesforgeks . org/python-program-to-sort-and-find-in-the-the-data-in-the-student-records/](https://www.geeksforgeeks.org/python-program-to-sort-and-find-the-data-in-the-student-records/)

考虑一个维护班级学生记录的软件。考虑需要执行的以下功能:

1.  根据学生的名字对名字进行排序。
2.  在所有标记中找到最小标记
3.  使用学生的名字查找他/她的联系号码。

任务是编写一个 Python 程序来实现具有这三种功能的软件。

**方法:**对于上述问题，我们应该使用一个字典，该字典要么将一个名称作为一个整体作为键，将其他数据作为值，要么相反。这里我把名字作为一个键和联系号码，标记为与名字相关联的值。因此，首先用户需要输入学生的详细信息，这些详细信息将作为{['名字'，'名字']:('联系电话'，'标记')}存储在字典中。然后我们根据功能需求创建一个新的存储数据的元组列表。在程序中，创建了四个用户定义的函数:

1.  **sort(** )函数，根据名字对记录进行排序。
2.  **minmarks( )** 从所有记录中找到最小标记的函数。
3.  **searchdetail( )** 函数，以名字为输入，从对应的记录中获取学生联系号码。
4.  **选项()**用于显示选项的功能。

下面是实现:

## 蟒蛇 3

```
print("-----Program for Student Information-----")

D = dict()

n = int(input('How many student record you want to store?? '))

# Add student information
# to the dictionary
for i in range(0,n):
    x, y = input("Enter the complete name (First and last name) of student: ").split()
    z = input("Enter contact number: ")
    m = input('Enter Marks: ')
    D[x, y] = (z, m)

# define a function for shorting
# names based on first name
def sort():
    ls = list()
    # fetch key and value using
    # items() method
    for sname,details in D.items():

        # store key parts as an tuple
        tup = (sname[0],sname[1])

        # add tuple to the list
        ls.append(tup)   

    # sort the final list of tuples
    ls = sorted(ls)   
    for i in ls:

        # print first name and second name
        print(i[0],i[1])
    return

# define a function for
# finding the minimum marks
# in stored data
def minmarks():
    ls = list()
    # fetch key and value using
    # items() methods
    for sname,details in D.items():
        # add details second element
        # (marks) to the list
        ls.append(details[1])   

    # sort the list elemnts   
    ls = sorted(ls)   
    print("Minimum marks: ", min(ls))

    return

# define a function for searching
# student contact number
def searchdetail(fname):
    ls = list()

    for sname,details in D.items():

        tup=(sname,details)
        ls.append(tup)

    for i in ls:
        if i[0][0] == fname:
            print(i[1][0])
    return

# define a function for
# asking the options
def option():

    choice = int(input('Enter the operation detail: \n \
    1: Sorting using first name \n \
    2: Finding Minimum marks \n \
    3: Search contact number using first name: \n \
    4: Exit\n \
    Option: '))

    if choice == 1:
        # function call
        sort()
        print('Want to perform some other operation??? Y or N: ')
        inp = input()
        if inp == 'Y':
            option()

        # exit function call   
        exit()

    elif choice == 2:
        minmarks()
        print('Want to perform some other operation??? Y or N: ')

        inp = input()
        if inp == 'Y':
            option()
        exit()

    elif choice == 3:
        first = input('Enter first name of student: ')
        searchdetail(first)

        print('Want to perform some other operation??? Y or N: ')
        inp = input()
        if inp == 'Y':
            option()

        exit()
    else:
        print('Thanks for executing me!!!!')
        exit()

option()
```

**输出:**

```
-----Program for Student Information-----
How many student record you want to store?? 3
Enter the complete name (First and last name) of student: shubham shukla
Enter contact number: 1234567890
Enter Marks: 85
Enter the complete name (First and last name) of student: rinki singh
Enter contact number: 0987654321
Enter Marks: 50
Enter the complete name (First and last name) of student: abhishek sharma
Enter contact number: 5432167890
Enter Marks: 65
Enter the operation detail: 
     1: Sorting using first name 
     2: Finding Minimum marks 
     3: Search contact number using first name: 
     4: Exit
     Option: 1
abhishek sharma
rinki singh
shubham shukla
Want to perform some other operation??? Y or N: 
Y
Enter the operation detail: 
     1: Sorting using first name 
     2: Finding Minimum marks 
     3: Search contact number using first name: 
     4: Exit
     Option: 2
Minimum marks:  50
Want to perform some other operation??? Y or N: 
Y
Enter the operation detail: 
     1: Sorting using first name 
     2: Finding Minimum marks 
     3: Search contact number using first name: 
     4: Exit
     Option: 3
Enter first name of student: rinki
0987654321
Want to perform some other operation??? Y or N: 
N
```