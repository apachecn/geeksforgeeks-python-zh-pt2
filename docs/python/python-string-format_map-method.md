# Python 字符串格式 _map()方法

> 原文:[https://www . geesforgeks . org/python-string-format _ map-method/](https://www.geeksforgeeks.org/python-string-format_map-method/)

Python 字符串*****format _ map()***方法是 Python 中的一个内置函数，用于返回字典键的值。**

> ****语法:****
> 
> **string.format_map(z)**
> 
>  ****参数:**
> 
> 这里 z 是存储输入字典的变量，字符串是输入字典的键。input_dict:接受单个参数，即输入字典。
> 
> **返回:**
> 
> 返回输入字典的键值。**

### **示例 1: Python 字符串格式 _map()方法**

## **蟒蛇 3**

```py
# input stored in variable a.
a = {'x':'John', 'y':'Wick'}

# Use of format_map() function
print("{x}'s last name is {y}".format_map(a))
```

****输出:****

```py
John's last name is Wick
```

### ****例 2:****

## **蟒蛇 3**

```py
# input stored in variable a.
a = {'x':"geeksforgeeks", 'y':'b'}

# Use of format_map() function
print('{x} {y}'.format_map(a))
```

****输出:****

```py
geeksforgeeks b
```

### **例 3:**

## **蟒蛇 3**

```py
# Input dictionary
profession = { 'name':['Barry', 'Bruce'],
               'profession':['Engineer', 'Doctor'],
               'age':[30, 31] }

# Use of format_map() function 
print('{name[0]} is an {profession[0]} and he'
      ' is {age[0]} years old.'.format_map(profession))

print('{name[1]} is an {profession[1]} and he'
      ' is {age[1]} years old.'.format_map(profession))
```

****输出:****

```py
Barry is an Engineer and he is 30 years old.
Bruce is an Doctor and he is 31 years old.
```

### ****例 4:** 实用**应用****

**format_map()函数可用于任何实际应用。**

## **蟒蛇 3**

```py
# Python code showing practical 
# use of format_map() function
def chk_msg(n):

    # input stored in variable a.
    a = {'name':"George", 'mesg':n}

    # use of format_map() function 
    print('{name} has {mesg} new messages'.format_map(a))

chk_msg(10)
```

****输出:****

```py
George has 10 new messages
```