# Python time.tzname()函数

> 原文:[https://www.geeksforgeeks.org/python-time-tzname-function/](https://www.geeksforgeeks.org/python-time-tzname-function/)

Python 中的 Time tzname()返回两个字符串的元组，其中第一个字符串是本地非 DST 时区的名称，第二个字符串是本地 DST 时区的名称。

> **语法** : time.tzname()
> 
> **返回**:将返回字符串的元组

### **例 1** : Python 程序获取夏令时和非夏令时

## 蟒蛇 3

```
# import time module
import time

# get the DST
print(time.tzname)
```

**输出:**

```
('UTC', 'UTC')
```

### **示例 2** :使用索引号获取字符串

## 蟒蛇 3

```
# import time module
import time

# get the DST of first string
print(time.tzname[0])

# get the DST of second string
print(time.tzname[1])
```

**输出:**

```
UTC
UTC
```