# Python 程序将列表的所有元素连接成一个字符串

> 原文:[https://www . geesforgeks . org/python-program-to-concatenate-all-elements-of-list-in-string/](https://www.geeksforgeeks.org/python-program-to-concatenate-all-elements-of-a-list-into-a-string/)

给定一个列表，任务是编写一个 Python 程序，将列表中的所有元素连接成一个字符串。

**示例:**

```
Input: ['hello', 'geek', 'have', 'a', 'geeky', 'day']
Output: hello geek have a geeky day

Input: ['did', 'u', 'like', 'my', 'article', '?']
Output: did u like my article ?
```

**方法 1:** 使用[连接()](https://www.geeksforgeeks.org/join-function-python/)方法

## 蟒蛇 3

```
# code
l = ['hello', 'geek', 'have',
   'a', '1', 'day']

# this will join all the 
# elements of the list with ' '
l = ' '.join(l) 
print(l)
```

**输出:**

```
hello geek have a 1 day
```

**方法 2:** 天真的方法

## 蟒蛇 3

```
l = [ 'hello', 'geek', 'have', 
     'a', 'geeky', 'day']

ans = ' '
for i in l: 

  # concatenating the strings
  # using + operator
  ans = ans+ ' '+i

print(ans)
```

**输出:**

```
hello geek have a geeky day
```