# Python–包含所有给定列表字符的字符串

> 原文:[https://www . geeksforgeeks . org/python-带有所有给定列表字符的字符串/](https://www.geeksforgeeks.org/python-strings-with-all-given-list-characters/)

给定字符串列表和字符列表，提取所有字符串，从字符列表中获取所有字符。

> **输入**:test _ list =[“Geeks”“Gfg”“Geeksforgeeks”“free”]，chr _ list =[‘f’，‘r’，‘e’]
> **输出**:[‘free’，‘Geeks forgeeks’]
> **解释**:只有“free”和“Geeks forgeeks”包含所有的‘f’，‘r’和‘e’。
> 
> **输入**:test _ list =[“Geeks”“Gfg”“Geeks forgeeks”“free”]，chr_list = ['x']
> **输出** : []
> **解释**:无字含‘x’。

**方法#1:使用循环**

在这种情况下，我们迭代列表中的所有元素，并检查是否所有元素都出现在特定的字符串中，如果是，则该字符串被附加到结果中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Strings with all List characters
# Using loop

# initializing list
test_list = ["Geeks", "Gfg", "Geeksforgeeks", "free"]

# printing original list
print("The original list is : " + str(test_list))

# initializing char_list 
chr_list = ['g', 'f']

res_list = []
for sub in test_list:
    res = True 
    for ele in chr_list:

        # check if any element is not present
        if ele not in sub:
            res = False 
            break
    if res:
        res_list.append(sub)

# printing results
print("Filtered Strings : " + str(res_list))
```

**Output**

```
The original list is : ['Geeks', 'Gfg', 'Geeksforgeeks', 'free']
Filtered Strings : ['Gfg', 'Geeksforgeeks']

```

**方法 2:使用 all() +列表理解**

在这种情况下，我们使用 all()检查所有字符是否存在，如果检查出来，字符串将被追加到结果中。迭代部分作为一行在列表理解中完成。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Strings with all List characters
# Using all() + list comprehension

# initializing list
test_list = ["Geeks", "Gfg", "Geeksforgeeks", "free"]

# printing original list
print("The original list is : " + str(test_list))

# initializing char_list 
chr_list = ['g', 'f']

# using all() to check containment of all characters
res_list = [sub for sub in test_list if all(ele in sub for ele in chr_list)]

# printing results
print("Filtered Strings : " + str(res_list))
```

**Output**

```
The original list is : ['Geeks', 'Gfg', 'Geeksforgeeks', 'free']
Filtered Strings : ['Gfg', 'Geeksforgeeks']

```