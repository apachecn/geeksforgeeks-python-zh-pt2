# 在 python 中设置 copy()

> 原文:[https://www.geeksforgeeks.org/set-copy-python/](https://www.geeksforgeeks.org/set-copy-python/)

copy()方法返回 python 中集合的浅拷贝。如果我们使用 **"="** 将一个集合复制到另一个集合，当我们在复制的集合中进行修改时，更改也会反映在原始集合中。因此，我们必须创建一个集合的浅拷贝，这样当我们修改拷贝集合中的某些内容时，更改不会反映回原始集合中。

**语法:**

```py
*set_name*.copy()

set_name: Name of the set whose copy
          we want to generate.

```

**参数:**集合的 copy()方法不接受任何参数。

**返回值:**该函数返回原始集合的浅拷贝。

下面是上述功能的实现:

```py
# Python3 program to demonstrate the use
# of join() function 

set1 = {1, 2, 3, 4} 

# function to copy the set
set2 = set1.copy() 

# prints the copied set
print(set2)       
```

输出:

```py
{1, 2, 3, 4} 

```

**浅复制示例:**

```py
# Python program to demonstrate that copy 
# created using set copy is shallow
first = {'g', 'e', 'e', 'k', 's'}
second = first.copy()

# before adding
print 'before adding: '
print 'first: ',first
print 'second: ', second 

# Adding element to second, first does not
# change.
second.add('f')

# after adding
print 'after adding: '
print 'first: ', first
print 'second: ', second 
```

输出:

```py
before adding: 
first:  set(['s', 'e', 'k', 'g'])
second:  set(['s', 'e', 'k', 'g'])
after adding: 
first:  set(['s', 'e', 'k', 'g'])
second:  set(['s', 'e', 'k', 'g', 'f'])

```