# Python 程序查找列表中最小的数字

> 原文:[https://www . geesforgeks . org/python-程序查找列表中最小的数字/](https://www.geeksforgeeks.org/python-program-to-find-smallest-number-in-a-list/)

给定一个数字列表，任务是编写一个 Python 程序来查找给定列表中的最小数字。
示例:

```py
Input : list1 = [10, 20, 4]
Output : 4

Input : list2 = [20, 10, 20, 1, 100]
Output : 1
```

方法 1:对列表进行升序排序，并打印列表中的第一个元素。

## 蟒蛇 3

```py
# Python program to find smallest
# number in a list

# list of numbers
list1 = [10, 20, 4, 45, 99]

# sorting the list
list1.sort()

# printing the first element
print("Smallest element is:", *list1[:1])
```

**输出:**

```py
smallest element is: 4
```

方法 2:使用 min()方法

## 蟒蛇 3

```py
# Python program to find smallest
# number in a list

# list of numbers
list1 = [10, 20, 1, 45, 99]

# printing the maximum element
print("Smallest element is:", min(list1))
```

**输出:**

```py
Smallest element is: 1
```

方法 3:根据用户提供的输入找到最小列表元素。

## 蟒蛇 3

```py
# Python program to find smallest
# number in a list

# creating empty list
list1 = []

# asking number of elements to put in list
num = int(input("Enter number of elements in list: "))

# iterating till num to append elements in list
for i in range(1, num + 1):
    ele= int(input("Enter elements: "))
    list1.append(ele)

# print maximum element
print("Smallest element is:", min(list1))
```

**输出:**

```py
Enter number of elements in list: 4
Enter elements: 12
Enter elements: 19
Enter elements: 11
Enter elements: 99
Smallest element is: 11
```

方法 4:找到列表中最小的元素。

## 蟒蛇 3

```py
# Python program to find smallest
# number in a list

l=[ int(l) for l in input("List:").split(",")]
print("The list is ",l)

# Assign first element as a minimum.
min1 = l[0]

for i in range(len(l)):

    # If the other element is min than first element
    if l[i] < min1:
        min1 = l[i] #It will change

print("The smallest element in the list is ",min1)
```

**输入:**

```py
List: 23,-1,45,22.6,78,100,-5
```

**输出:**

```py
The list is ['23', '-1', '45', '22.6', '78', '100','-5']
The smallest element in the list is  -5
```