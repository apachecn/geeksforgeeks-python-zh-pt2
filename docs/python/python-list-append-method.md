# Python 列表追加()方法

> 原文:[https://www.geeksforgeeks.org/python-list-append-method/](https://www.geeksforgeeks.org/python-list-append-method/)

Python List ***追加()*** 方法用于在[列表](https://www.geeksforgeeks.org/python-list/)的末尾追加和添加元素。

> **语法:**列表.追加(项)
> 
> **参数:**
> 
> *   **项:**列表末尾要添加的项
> 
> **返回:**
> 
> 该方法不返回值

### **示例 1:向列表中添加项目**

## 计算机编程语言

```
# my_list
my_list = ['geeks', 'for']

# Add 'geeks' to the list
my_list.append('geeks')

print my_list
```

**输出:**

```
['geeks', 'for', 'geeks']
```

### **示例 2:向列表中添加列表**

## 计算机编程语言

```
# my_list
my_list = ['geeks', 'for', 'geeks']

# another list
another_list = [6, 0, 4, 1]

# append another_list to my_list
my_list.append(another_list)

print my_list
```

**输出:**

```
['geeks', 'for', 'geeks', [6, 0, 4, 1]]
```

**注**:列表就是一个对象。如果将另一个列表追加到列表中，参数列表将是列表末尾的单个对象。