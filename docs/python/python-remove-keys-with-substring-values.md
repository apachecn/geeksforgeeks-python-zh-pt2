# Python–移除带有子字符串值的键

> 原文:[https://www . geesforgeks . org/python-remove-key-with-substring-values/](https://www.geeksforgeeks.org/python-remove-keys-with-substring-values/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要移除值包含子字符串作为参数的键。这个问题可能发生在 web 开发和日常编程的情况下。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_dict = {1 : 'Gfg 最适合极客' }
> 子列表= ['love '，' good'](检查值的字符串)
> **输出** : {1: 'Gfg 最适合极客' }
> 
> **输入** :
> test_dict = {1 : 'Gfg 是爱'，2: 'Gfg 是好' }
> 子列表= ['爱'，'好'](字符串检查值)
> T5】输出 : {}

**方法#1:使用`any()` +循环**
以上功能的组合可以用来解决这个问题。在这种情况下，我们从字典中提取所有没有所需值的项目，使用任何()和生成器表达式执行过滤。

```py
# Python3 code to demonstrate working of 
# Remove keys with substring values
# Using any() + generator expression

# initializing dictionary
test_dict = {1 : 'Gfg is best for geeks', 2 : 'Gfg is good', 3 : 'I love Gfg'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing substrings
sub_list = ['love', 'good']

# Remove keys with substring values
# Using any() + generator expression
res = dict()
for key, val in test_dict.items():
   if not any(ele in val for ele in sub_list):
       res[key] = val

# printing result 
print("Filtered Dictionary : " + str(res)) 
```

**Output :**

> 原版词典:{1: 'Gfg 最适合极客'，2: 'Gfg 很好'，3:'我爱 Gfg'}
> 过滤词典:{1: 'Gfg 最适合极客' }

**方法 2:使用字典理解+ `any()`**
以上方法的组合提供了执行该任务的速记。在这种情况下，我们以与上述方法类似的方式执行该任务，但是使用理解的一种线性格式。

```py
# Python3 code to demonstrate working of 
# Remove keys with substring values
# Using dictionary comprehension + any()

# initializing dictionary
test_dict = {1 : 'Gfg is best for geeks', 2 : 'Gfg is good', 3 : 'I love Gfg'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing substrings
sub_list = ['love', 'good']

# Remove keys with substring values
# Using dictionary comprehension + any()
res = {key : val for key, val in test_dict.items() if not any(ele in val for ele in sub_list)}

# printing result 
print("Filtered Dictionary : " + str(res)) 
```

**Output :**

```py
The original dictionary : {1: 'Gfg is best for geeks', 2: 'Gfg is good', 3: 'I love Gfg'}
Filtered Dictionary : {1: 'Gfg is best for geeks'}

```