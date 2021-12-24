# Python 程序按子串范围对字符串进行排序

> 原文:[https://www . geesforgeks . org/python-程序-按子字符串范围对字符串进行排序/](https://www.geeksforgeeks.org/python-program-to-sort-strings-by-substring-range/)

给定字符串列表，按子字符串范围排序。

> **输入** : test_list = [“极客 forgeeks”、“最佳”、“极客”、“准备”、“面试”]，I，j = 1，3
> **输出** : [“极客 forgeeks”、“极客”、“最佳”、“面试”、“准备”]
> 
> **解释**:【eek】<【eek】<【est】<【NTE】<【rep】。
> 
> **输入** : test_list = [“苹果”、“橘子”、“香蕉”]，I、j = 2、4
> **输出** : [“橘子”、“香蕉”、“苹果”]
> **解释**:“ang”<“nan”<“ple”。

**方法#1:使用 sort() +切片**

在本文中，我们使用 sort()执行排序任务，使用切片完成提取范围的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Strings By Substring Range
# Using sort() + slicing

# helper function
def get_substr(test_str):

    # getting range
    return test_str[i : j]

# initializing list
test_list = ["geeksforgeeks", "best", "geeks", "preparation"]

# printing original list
print("The original list is : " + str(test_list))

# initializing range 
i, j = 1, 3

# calling func.
test_list.sort(key=get_substr)

# printing result 
print("Strings after sorting : " + str(test_list))
```

**Output**

> 原列表为:['极客 forgeeks '，'最佳'，'极客'，'准备']
> 排序后的字符串:['极客 forgeeks '，'极客'，'最佳'，'准备'

**方法 2:使用 lambda 函数+ sort() +切片**

在本文中，我们使用 lambda 函数而不是调用外部函数来执行切片。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Strings By Substring Range
# Using lambda function + sort() + slicing

# initializing list
test_list = ["geeksforgeeks", "best", "geeks", "preparation"]

# printing original list
print("The original list is : " + str(test_list))

# initializing range 
i, j = 1, 3

# lambda function providing sort fnc.
test_list.sort(key=lambda test_str : test_str[i : j])

# printing result 
print("Strings after sorting : " + str(test_list))
```

**Output**

> 原列表为:['极客 forgeeks '，'最佳'，'极客'，'准备']
> 排序后的字符串:['极客 forgeeks '，'极客'，'最佳'，'准备'