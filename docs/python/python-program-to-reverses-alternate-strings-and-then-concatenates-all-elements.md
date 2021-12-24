# Python 程序反转替换字符串，然后连接所有元素

> 原文:[https://www . geesforgeks . org/python-program-to-reverse-alternate-string-然后-concatenates-all-elements/](https://www.geeksforgeeks.org/python-program-to-reverses-alternate-strings-and-then-concatenates-all-elements/)

给定一个字符串列表，下面的程序返回一个所有字符串元素的串联列表，其中替换元素是反向的。

> **输入** : test_str = '极客最适合极客'
> **输出**:skegskeg 最适合极客
> **解释**:交替词颠倒。
> **输入**:test _ str = ' geeks geeks best geeks '
> **输出**:skegskeg best skeg
> **解释**:交替字颠倒。

**方法 1 :** *使用* [*反过来()*](https://www.geeksforgeeks.org/python-list-reverse/#:~:text=reverse()%20is%20an%20inbuilt,objects%20of%20list%20in%20place.&text=Returns%3A,given%20object%20from%20the%20list.) *和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在本例中，我们使用 reversed()执行反转字符串的任务，然后使用%运算符检查备选项，并相应地进行连接。

## 蟒蛇 3

```py
# initializing string
test_str = 'geeksgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# splitting string
temp = test_str.split()

res = []
for idx in range(len(temp)):

    # reversing if alternate
    if idx % 2 == 0:
        res.append(''.join(list(reversed(temp[idx]))))
    else :
        res.append(temp[idx])

res = ' '.join(res)

# printing result
print("Transformed String : " + str(res))
```

**输出:**

> 最初的字符串是:极客最适合极客
> 
> 变形弦:斯基格斯基格是斯基格的简称

**方法二:** *使用* [*切片*](https://www.geeksforgeeks.org/string-slicing-in-python/) *和* [*列表理解*](https://www.geeksforgeeks.org/comprehensions-in-python/)

在这种情况下，我们使用切片来执行反向任务，然后使用列表理解来执行循环完成的任务。

## 蟒蛇 3

```py
# initializing string
test_str = 'geeksgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# splitting string
temp = test_str.split()

# list comprehension to solve problem in 1 liner
res = ' '.join([''.join(list(reversed(temp[idx]))) if idx % 2 == 0 else temp[idx] for idx in range(len(temp))])

# printing result
print("Transformed String : " + str(res))
```

**输出:**

> 最初的字符串是:极客最适合极客
> 
> 变形弦:斯基格斯基格是斯基格的简称