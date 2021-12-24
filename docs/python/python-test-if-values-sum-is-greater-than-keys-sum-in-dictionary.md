# Python–测试字典中的值总和是否大于键总和

> 原文:[https://www . geesforgeks . org/python-test-if-values-sum-大于 key-sum-in-dictionary/](https://www.geeksforgeeks.org/python-test-if-values-sum-is-greater-than-keys-sum-in-dictionary/)

给定一个字典，检查值的总和是否大于键的总和。

> **输入** : test_dict = {5:3，1:3，10:4，7:3，8:1，9:5}
> **输出** : False
> **解释** : Values sum = 19 < 40，为关键和，即 False。
> 
> **输入** : test_dict = {5:3，1:4}
> **输出**:真
> **解释**:值和= 7 > 6，为关键和，即真。

**方法#1:使用循环**

在这种情况下，我们在单独的计数器中计算键和值的总和，并且在循环使这些值相等之后，如果值大于键总和，则返回真。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if Values Sum is Greater than Keys Sum in dictionary
# Using loop

# initializing dictionary
test_dict = {5: 3, 1: 3, 10: 4, 7: 3, 8: 1, 9: 5}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

key_sum = 0
val_sum = 0

for key in test_dict:

    # getting sum
    key_sum += key
    val_sum += test_dict[key]

# checking if val_sum greater than key sum
res = val_sum > key_sum

# printing result
print("The required result : " + str(res))
```

**Output**

```
The original dictionary is : {5: 3, 1: 3, 10: 4, 7: 3, 8: 1, 9: 5}
The required result : False

```

**方法 2:使用 sum()+values()+key()**

这样，使用键()提取键和值总和，使用和()提取值总和，检查所需条件并计算结论。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if Values Sum is Greater than Keys Sum in dictionary
# Using sum() + values()  + keys()

# initializing dictionary
test_dict = {5: 3, 1: 3, 10: 4, 7: 3, 8: 1, 9: 5}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = sum(list(test_dict.keys())) < sum(list(test_dict.values()))

# printing result
print("The required result : " + str(res))
```

**Output**

```
The original dictionary is : {5: 3, 1: 3, 10: 4, 7: 3, 8: 1, 9: 5}
The required result : False

```