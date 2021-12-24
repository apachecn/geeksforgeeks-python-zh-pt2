# Python 程序将数字移动到字符串的末尾

> 原文:[https://www . geesforgeks . org/python-program-to-move-numbers-to-end-the-string/](https://www.geeksforgeeks.org/python-program-to-move-numbers-to-the-end-of-the-string/)

给定一个字符串，任务是编写一个 Python 程序，将其中的所有数字移动到它的末尾。

**示例:**

> **输入**:test _ str = ' geek 2 eeks4g 1 eek 5 sbest6 for All 9 '
> **输出**:geek 2 eeksgeeksbestforall 241569
> **解释**:所有数字移动到结尾。
> 
> **输入**:test _ str = ' geekesg1eek5sbest6 for All 9 '
> **输出**:geekesgeeksbestforall 1569
> **解释**:所有数字移动到结尾。

**方法 1 :** *使用*[T5【is digit()](https://www.geeksforgeeks.org/python-string-isdigit-application/)*和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在本文中，我们使用 isdigit()检查元素和数字，跟踪所有数字，并在字符串后迭代结束时追加。

## 蟒蛇 3

```
# initializing string
test_str = 'geek2eeks4g1eek5sbest6forall9'

# printing original string
print("The original string is : " + str(test_str))

# getting all numbers and removing digits
res = ''
dig = ''
for ele in test_str:
    if ele.isdigit():
        dig += ele
    else:
        res += ele

# adding digits at end
res += dig

# printing result
print("Strings after digits at end : " + str(res))
```

**输出:**

> 原始字符串为:geek2eeks4g1eek5sbest6forall9
> 
> 结尾数字后的字符串:geekeeksgeeksbestforall241569

**方法二:** *使用* [*加入()*](https://www.geeksforgeeks.org/join-function-python/)

在这种情况下，我们执行提取数字的任务，并使用单独的理解来忽略它们，然后将两者结合起来。在末尾，数字串被连接在实际串的末尾。

## 蟒蛇 3

```
# initializing string
test_str = 'geek2eeks4g1eek5sbest6forall9'

# printing original string
print("The original string is : " + str(test_str))

# getting all numbers
dig = ''.join(ele for ele in test_str if ele.isdigit())

# getting all elements not digit
res = ''.join(ele for ele in test_str if not ele.isdigit())

# adding digits at end
res += dig

# printing result
print("Strings after digits at end : " + str(res))
```

**输出:**

> 原始字符串为:geek2eeks4g1eek5sbest6forall9
> 
> 结尾数字后的字符串:geekeeksgeeksbestforall241569