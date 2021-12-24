# Python 列表清除()方法

> 原文:[https://www.geeksforgeeks.org/python-list-clear-method/](https://www.geeksforgeeks.org/python-list-clear-method/)

Python List***clear()****方法用于从[列表](https://www.geeksforgeeks.org/python-list/)中移除所有项目。*

> ***语法:** list.clear()*
> 
> ***参数:***
> 
>  *clear()方法不接受任何参数
> 
> **返回:**
> 
> 该方法不返回值*

### ***例 1:使用列表**中的 clear()方法*

## *蟒蛇 3*

```py
*# Python program to clear a list
# using clear() method

# Creating list
GEEK = [6, 0, 4, 1]
print('GEEK before clear:', GEEK)

# Clearing list
GEEK.clear()
print('GEEK after clear:', GEEK)*
```

***输出:***

```py
*GEEK before clear: [6, 0, 4, 1]
GEEK after clear: []*
```

### ***例 2:***

## *蟒蛇 3*

```py
*# Defining a list
list = [{1, 2, 3, 4}, ['1.1', '2.2']]

# clearing the list
list.clear()

print(list)*
```

***输出:***

```py
*[]*
```