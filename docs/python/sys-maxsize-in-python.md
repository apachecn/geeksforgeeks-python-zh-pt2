# Python 中的 sys.maxsize()

> 原文:[https://www.geeksforgeeks.org/sys-maxsize-in-python/](https://www.geeksforgeeks.org/sys-maxsize-in-python/)

**系统**模块的 **maxsize** 属性获取数据类型**Py _ ssize _ t****可以存储的最大值 a 变量。正是 Python 平台的指针规定了 Python 中列表和字符串的最大大小。maxsize 返回的大小值取决于平台架构:**

*   ****32 位:**值为 2^31-1，即 2147483647**
*   ****64 位:**值为 2^63-1，即 9223372036854775807**

### **sys.maxsize**

> ****语法:** sys.maxsize**
> 
> ****返回:**Py _ ssize _ t 的最大值，具体取决于架构**

****示例 1:** 让我们获取 64 位系统上的最大 Py_ssize_t 值。**

## **蟒蛇 3**

```
# importing the module
import sys

# fetching the maximum value
max_val = sys.maxsize
print(max_val)
```

****输出:****

```
9223372036854775807
```

****示例 2:** 创建最大大小的列表。**

## **蟒蛇 3**

```
# importing the module
import sys

# fetching the maximum value
max_val = sys.maxsize

# creating list with max size
list = range(max_val)

# displaying the length of the list
print(len(list))

print("List successfully created")
```

****Output**

```
9223372036854775807
List successfully created

```** 

****输出:****

```
9223372036854775807
List successfully created
```

****示例 3:** 试图创建一个大于最大大小的列表。**

## **蟒蛇 3**

```
# importing the module
import sys

# fetching the maximum value
max_val = sys.maxsize

try:

    # creating list with max size + 1
    list = range(max_val + 1)

    # displaying the length of the list
    print(len(list))
    print("List successfully created")

except Exception as e:

    # displaying the exception
    print(e)
    print("List creation unsuccessful")
```

****Output**

```
Python int too large to convert to C ssize_t
List creation unsuccessful

```** 

****输出:****

```
Python int too large to convert to C ssize_t
List creation unsuccessful
```