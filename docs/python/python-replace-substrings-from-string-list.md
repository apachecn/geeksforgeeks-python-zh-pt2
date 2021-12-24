# Python–替换字符串列表中的子字符串

> 原文:[https://www . geesforgeks . org/python-replace-substrings-from-string-list/](https://www.geeksforgeeks.org/python-replace-substrings-from-string-list/)

有时在处理数据时，我们会遇到一个问题，即我们需要用映射的字符串执行替换子字符串，以形成一些术语的简短形式。这种问题在许多涉及数据的领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop+replace()+enumerate()**
以上功能的组合可以用来执行这个任务。在本例中，我们使用 loop 和 enumerate()执行迭代任务，并使用 replace()完成较短形式的替换。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Replace Substrings from String List
# using loop + replace() + enumerate()

# Initializing list1
test_list1 = ['GeeksforGeeks', 'is', 'Best', 'For', 'Geeks', 'And', 'Computer Science']
test_list2 = [['Geeks', 'Gks'], ['And', '&'], ['Computer', 'Comp']]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Replace Substrings from String List
# using loop + replace() + enumerate()
sub = dict(test_list2)
for key, val in sub.items():
    for idx, ele in enumerate(test_list1):
        if key in ele:
            test_list1[idx] = ele.replace(key, val)

# printing result
print ("The list after replacement : " + str(test_list1))
```

**Output : **

```
The original list 1 is : ['GeeksforGeeks', 'is', 'Best', 'For', 'Geeks', 'And', 'Computer Science']
The original list 2 is : [['Geeks', 'Gks'], ['And', '&'], ['Computer', 'Comp']]
The list after replacement : ['GksforGks', 'is', 'Best', 'For', 'Gks', '&', 'Comp Science']
```

**方法 2:使用 replace() +列表理解**
这是可以执行此任务的另一种方式。在本例中，我们使用 replace()执行替换任务，其余任务使用列表理解执行。它删除没有替换的列表。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Replace Substrings from String List
# using replace() + list comprehension

# Initializing list1
test_list1 = ['GeeksforGeeks', 'is', 'Best', 'For', 'Geeks', 'And', 'Computer Science']
test_list2 = [['Geeks', 'Gks'], ['And', '&'], ['Computer', 'Comp']]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Replace Substrings from String List
# using replace() + list comprehension
res = [sub.replace(sub2[0], sub2[1]) for sub in test_list1
      for sub2 in test_list2 if sub2[0] in sub]

# printing result
print ("The list after replacement : " + str(res))
```

**Output : **

```
The original list 1 is : ['GeeksforGeeks', 'is', 'Best', 'For', 'Geeks', 'And', 'Computer Science']
The original list 2 is : [['Geeks', 'Gks'], ['And', '&'], ['Computer', 'Comp']]
The list after replacement : ['GksforGks', 'Gks', '&', 'Comp Science']
```