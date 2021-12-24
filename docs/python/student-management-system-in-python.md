# Python 中的学生管理系统

> 原文:[https://www . geesforgeks . org/student-management-system-in-python/](https://www.geeksforgeeks.org/student-management-system-in-python/)

**先决条件:**[python 中的类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)

**问题陈述:**
用 Python 编写一个程序，构建一个简单的学生管理系统，可以执行以下操作:

1.  接受
2.  显示
3.  搜索
4.  删除
5.  更新

**进场:**下面是做以上操作的进场:

1.  **接受**–该方法从用户那里获取两个不同主题的详细信息，如姓名、卷号和标记。

    ```py
    # Method to enter new student details
    def accept(self, Name, Rollno, marks1, marks2 ):
        # Creates a new class constructor
        # and pass the details
        ob = Student(Name, Rollno, marks1, marks2 )

        # list containing objects of student class
        ls.append(ob)

    ```

2.  **显示**–此方法显示每个学生的详细信息。

    ```py
    # Function to display student details     
    def display(self, ob):
        print("Name   : ", ob.name)
        print("RollNo : ", ob.rollno)
        print("Marks1 : ", ob.m1)
        print("Marks2 : ", ob.m2)
        print("\n")    

    ```

3.  **搜索**–该方法从学生列表中搜索特定的学生。
    该方法会向用户询问辊号，然后根据辊号

    ```py
    # Search Function    
    def search(self, rn):
        for i in range(ls.__len__()):
            # iterate through the list containing
            # student object and checks through
            # roll no of each object
            if(ls[i].rollno == rn):
                # returns the object with matching 
                # roll number
                return i 

    ```

    进行搜索
4.  **删除**–该方法删除具有匹配学号的特定学生的记录。

    ```py
    # Delete Function                                  
    def delete(self, rn):
        # Calls the search function 
        # created above
        i = obj.search(rn)  
        del ls[i]

    ```

5.  **Update** – This method updates the roll number of the student.
    This method will ask for the old roll number and new roll number. It will replace the old roll number with new roll number.

    ```py
    # Update Function   
    def update(self, rn, No):
        # calling the search function
        # of student class
        i = obj.search(rn)
        ls[i].rollno = No

    ```

    下面是上述方法的实现:

    ```py
    # This is simplest Student data management program in python
    # Create class "Student"
    class Student:
        # Constructor
        def __init__(self, name, rollno, m1, m2):
            self.name = name
            self.rollno = rollno
            self.m1 = m1
            self.m2 = m2

        # Function to create and append new student   
        def accept(self, Name, Rollno, marks1, marks2 ):
            # use  ' int(input()) ' method to take input from user
            ob = Student(Name, Rollno, marks1, marks2 )
            ls.append(ob)

        # Function to display student details     
        def display(self, ob):
                print("Name   : ", ob.name)
                print("RollNo : ", ob.rollno)
                print("Marks1 : ", ob.m1)
                print("Marks2 : ", ob.m2)
                print("\n")    

        # Search Function    
        def search(self, rn):
            for i in range(ls.__len__()):
                if(ls[i].rollno == rn):
                    return i       

        # Delete Function                                  
        def delete(self, rn):
            i = obj.search(rn)  
            del ls[i]

        # Update Function   
        def update(self, rn, No):
            i = obj.search(rn)
            roll = No
            ls[i].rollno = roll;

    # Create a list to add Students
    ls =[]
    # an object of Student class
    obj = Student('', 0, 0, 0)

    print("\nOperations used, ")
    print("\n1.Accept Student details\n2.Display Student Details\n" /
          / "3.Search Details of a Student\n4.Delete Details of Student" /
          / "\n5.Update Student Details\n6.Exit")

    # ch = int(input("Enter choice:"))
    # if(ch == 1):
    obj.accept("A", 1, 100, 100)
    obj.accept("B", 2, 90, 90)
    obj.accept("C", 3, 80, 80)

    # elif(ch == 2):
    print("\n")
    print("\nList of Students\n")
    for i in range(ls.__len__()):    
        obj.display(ls[i])

    # elif(ch == 3):
    print("\n Student Found, ")
    s = obj.search(2)
    obj.display(ls[s])

    # elif(ch == 4):
    obj.delete(2)
    print(ls.__len__())
    print("List after deletion")
    for i in range(ls.__len__()):    
        obj.display(ls[i])

    # elif(ch == 5):
    obj.update(3, 2)
    print(ls.__len__())
    print("List after updation")
    for i in range(ls.__len__()):    
        obj.display(ls[i])

    # else:
    print("Thank You !")

    ```

    **Output:**

    ```py
    Operations used,

    1.Accept Student details
    2.Display Student Details
    3.Search Details of a Student
    4.Delete Details of Student
    5.Update Student Details
    6.Exit

    List of Students

    Name   :  A
    RollNo :  1
    Marks1 :  100
    Marks2 :  100

    Name   :  B
    RollNo :  2
    Marks1 :  90
    Marks2 :  90

    Name   :  C
    RollNo :  3
    Marks1 :  80
    Marks2 :  80

     Student Found,
    Name   :  B
    RollNo :  2
    Marks1 :  90
    Marks2 :  90

    2
    List after deletion
    Name   :  A
    RollNo :  1
    Marks1 :  100
    Marks2 :  100

    Name   :  C
    RollNo :  3
    Marks1 :  80
    Marks2 :  80

    2
    List after updation
    Name   :  A
    RollNo :  1
    Marks1 :  100
    Marks2 :  100

    Name   :  C
    RollNo :  2
    Marks1 :  80
    Marks2 :  80

    Thank You !

    ```