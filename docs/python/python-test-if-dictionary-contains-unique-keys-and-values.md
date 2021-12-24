# Python |测试字典是否包含唯一的键和值

> 原文:[https://www . geesforgeks . org/python-test-if-dictionary-contains-unique-key-and-values/](https://www.geeksforgeeks.org/python-test-if-dictionary-contains-unique-keys-and-values/)

有时，我们只是希望使用独特的元素，任何类型的重复都是不希望的，对于这些情况，我们需要有技术来解决这些问题。一个这样的问题是测试唯一的键和值。对于键，默认情况下它们是唯一的，因此不需要外部测试，但是对于值，我们需要有方法来做到这一点。让我们测试一下实现这一点的各种方法。

**方法#1:使用循环**
在执行这个特定任务的朴素方法中，我们可以检查每个值，并将每个值插入字典中的列表/散列中，当重复发生时，只需停止流程并返回 false。

```
# Python3 code to demonstrate
# check for unique values
# Using loops

# initializing dictionary
test_dict = {'Manjeet' : 1, 'Akash' : 2, 'Akshat' : 3, 'Nikhil' : 1}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# using loops
# check for unique values
flag = False
hash_val = dict()
for keys in test_dict:
    if test_dict[keys] in hash_val:
        flag = True
        break
    else :
        hash_val[test_dict[keys]] = 1

# print result
print("Does dictionary contain repetition : " + str(flag))
```

**Output :**

```
The original dictionary : {'Nikhil': 1, 'Akash': 2, 'Akshat': 3, 'Manjeet': 1}
Does dictionary contain repetition : True

```