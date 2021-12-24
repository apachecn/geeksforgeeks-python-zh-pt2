# Python 程序将嵌套列表展平为元组列表

> 原文:[https://www . geesforgeks . org/python-程序-扁平化-嵌套-列表-元组-列表/](https://www.geeksforgeeks.org/python-program-to-flatten-nested-list-to-tuple-list/)

给定一个元组列表，每个元组围绕多个列表，我们的任务是编写一个 Python 程序，将容器展平为元组列表。

> **输入:** test_list = [[[(4，6)]]，[[(7，4)]]，[[[[(10，3)]]]
> 
> **输出:** [(4，6)，(7，4)，(10，3)]
> 
> **说明:**在每个元组周围省略了包围列表。
> 
> **输入:**test _ list =[[(4，6)]，[[(7，4)]]]
> 
> **输出:** [(4，6)，(7，4)]
> 
> **说明:**在每个元组周围省略了包围列表。

**方法#1:使用** [**递归**](https://www.geeksforgeeks.org/recursion/)**+**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)

在本例中，使用 isinstance()将容器包装测试为列表包装。递归策略用于检查列表的重复展平直到元组。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Multiflatten Tuple List
# Using recursion + isinstance()

res = []
def remove_lists(test_list):
    for ele in test_list:

        # checking for wrapped list
        if isinstance(ele, list):
            remove_lists(ele)
        else:
            res.append(ele)
    return res

# initializing list
test_list = [[[(4, 6)]], [[[(7, 4)]]], [[[[(10, 3)]]]]]

# printing original list
print("The original list is : " + str(test_list))

# calling recursive function
res = remove_lists(test_list)

# printing result
print("The Flattened container : " + str(res))
```

**输出:**

> 原来的名单是:[[[(4，6)]]，[[[(7，4)]]，[[[(10，3)]]]]
> 
> 扁平容器:[(4，6)，(7，4)，(10，3)]

**方法二:利用** [**屈服**](https://www.geeksforgeeks.org/python-yield-keyword/) **+递归**

这个方法使用递归执行类似的任务。生成器用于使用 yield 关键字处理中间结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Multiflatten Tuple List
# Using yield + recursion

def remove_lists(test_list):
    if isinstance(test_list, list):

        # return intermediate to recursive function
        for ele in test_list:
            yield from remove_lists(ele)
    else:
        yield test_list

# initializing list
test_list = [[[(4, 6)]], [[[(7, 4)]]], [[[[(10, 3)]]]]]

# printing original list
print("The original list is : " + str(test_list))

# calling recursive function
res = list(remove_lists(test_list))

# printing result
print("The Flattened container : " + str(res))
```

**输出:**

> 原来的名单是:[[[(4，6)]]，[[[(7，4)]]，[[[(10，3)]]]]
> 
> 扁平容器:[(4，6)，(7，4)，(10，3)]