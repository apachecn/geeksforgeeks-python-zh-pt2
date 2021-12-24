# Python–字符串的镜像

> 原文:[https://www . geesforgeks . org/python-镜像字符串/](https://www.geeksforgeeks.org/python-mirror-image-of-string/)

给定一个字符串，执行其镜像，如果镜像不可能使用英文字符，则返回“不可能”。

> **输入** : test_str = 'boid'
> **输出** : doib
> **解释** : d 替换为 b，反之为镜像。
> 
> **输入** : test_str = 'gfg'
> **输出**:不可能
> **解释**:有效镜像不可能。

**方法:使用 loop+loop 字典**

这是执行这项任务的一种方式。在这种情况下，我们为所有有效的可映射英文字符构造查找字典，然后从它们执行访问任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Mirror Image of String
# Using Mirror Image of String

# initializing strings
test_str = 'void'

# printing original string
print("The original string is : " + str(test_str))

# initializing mirror dictionary
mir_dict = {'b':'d', 'd':'b', 'i':'i', 'o':'o', 'v':'v', 'w':'w', 'x':'x'}
res = ''

# accessing letters from dictionary
for ele in test_str:
    if ele in mir_dict:
        res += mir_dict[ele]

    # if any character not present, flagging to be invalid 
    else:
        res = "Not Possible"
        break

# printing result 
print("The mirror string : " + str(res)) 
```

**Output**

```py
The original string is : void
The mirror string : voib

```