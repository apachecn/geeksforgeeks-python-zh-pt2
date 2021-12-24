# Python 程序以表格格式打印字典

> 原文:[https://www . geesforgeks . org/python-program-to-print-the-dictionary-in-table-format/](https://www.geeksforgeeks.org/python-program-to-print-the-dictionary-in-table-format/)

给一本字典。任务是以表格格式打印字典。
**例:**

> **输入:**T2:{ 1:【“Samuel”，21，【数据结构】，
> 2:【“Richie”，20，【机器学习】，
> 3:【“Lauren”，21，【OOPS with java】，
> }
> **输出:**
> NAME AGE COURSE
> Samuel 21 数据结构
> Richie 20 机器学习
> Lauren 21 OOPS with java

**方法 1:** 通过迭代值显示结果。

## 蟒蛇 3

```
# Define the dictionary
dict ={}

# Insert data into dictionary
dict1 = {1: ["Samuel", 21, 'Data Structures'],
     2: ["Richie", 20, 'Machine Learning'],
     3: ["Lauren", 21, 'OOPS with java'],
     }

# Print the names of the columns.
print ("{:<10} {:<10} {:<10}".format('NAME', 'AGE', 'COURSE'))

# print each data item.
for key, value in dict1.items():
    name, age, course = value
    print ("{:<10} {:<10} {:<10}".format(name, age, course))
```

**输出:**

```
NAME       AGE        COURSE    
Samuel     21         Data Structures
Richie     20         Machine Learning
Lauren     21         OOPS with java
```

**方法二:**采用矩阵格式显示

## 蟒蛇 3

```
# define the dictionary
dict1 = {}

# insert data into dictionary
dict1 = {(0, 0): 'Samuel', (0, 1): 21, (0, 2): 'Data structures',
         (1, 0): 'Richie', (1, 1): 20, (1, 2): 'Machine Learning',
         (2, 0): 'Lauren', (2, 1):21, (2, 2): 'OOPS with Java'
}

# print the name of the columns explicitly.
print(" NAME ", " AGE ", "  COURSE " )

# Iterate through the dictionary
# to print the data.
for i in range(3):

    for j in range(3):
        print(dict1[(i, j)], end ='   ')

    print()
```

**输出:**

```
 NAME   AGE    COURSE 
Samuel   21   Data structures   
Richie   20   Machine Learning   
Lauren   21   OOPS with Java 
```

**方法 3:** 使用 zip 格式显示

## 蟒蛇 3

```
# define the dictionary
dict1 = {}

# insert data into dictionary.
dict1 = {'NAME':['Samuel', 'Richie', 'Lauren'],
         'AGE':[21, 20, 21],
         'COURSE':['Data Structures', 'Machine Learning', 'OOPS with Java']}

# print the contents using zip format.
for each_row in zip(*([i] + (j)
                      for i, j in dict1.items())):

      print(*each_row, " ")
```

**输出:**

```
NAME  AGE COURSE  
Samuel 21 Data Structures  
Richie 20 Machine Learning  
Lauren 21 OOPS with Java
```