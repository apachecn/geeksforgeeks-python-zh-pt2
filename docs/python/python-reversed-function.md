# Python 反向()函数

> 原文:[https://www.geeksforgeeks.org/python-reversed-function/](https://www.geeksforgeeks.org/python-reversed-function/)

**Python reversed()方法**返回一个迭代器，以相反的顺序访问给定的序列。

### **Python 反转()语法**

> 反转(续)

### **Python 反向()参数**

> **序列:**要反转的序列。

### **Python 反转()返回**

> 返回以相反顺序访问给定序列的迭代器。

## 如何使用 Python 中的**反转方法？**

### **例 1:**Python 反向()方法演示

**这里我们使用元组和范围。**

## **蟒蛇 3**

```py
# Python code to demonstrate working of
# reversed()

# For tuple
seqTuple = ('g', 'e', 'e', 'k', 's')
print(list(reversed(seqTuple)))

# For range
seqRange = range(1, 5)
print(list(reversed(seqRange)))
```

****输出:****

```py
['s', 'k', 'e', 'e', 'g']
[4, 3, 2, 1]
```

### **示例 2:自定义对象中的反转()**

## **蟒蛇 3**

```py
class gfg:
    vowels = ['a', 'e', 'i', 'o', 'u']

    # Function to reverse the list
    def __reversed__(self):
        return reversed(self.vowels)

# Main Function   
if __name__ == '__main__':
    obj = gfg()
    print(list(reversed(obj)))
```

****输出:****

```py
['u', 'o', 'i', 'e', 'a']
```

### **示例 3: Python 列表反向()**

## **蟒蛇 3**

```py
vowels = ['a', 'e', 'i', 'o', 'u']
print(list(reversed(vowels)))
```

****输出:****

```py
['u', 'o', 'i', 'e', 'a']
```

### **示例 4: Python 反向()字符串**

## **蟒蛇 3**

```py
str = "Geeksforgeeks"
print(list(reversed(str)))
```

****输出:****

```py
['s', 'k', 'e', 'e', 'g', 'r', 'o', 'f', 's', 'k', 'e', 'e', 'G']
```

### **示例 5: Python 反向()列表**

## **蟒蛇 3**

```py
# For list
seqList = [1, 2, 4, 3, 5]
print(list(reversed(seqList)))
```

****输出:****

```py
[5, 3, 4, 2, 1]
```