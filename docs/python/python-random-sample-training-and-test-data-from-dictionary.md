# Python–字典中的随机样本训练和测试数据

> 原文:[https://www . geesforgeks . org/python-random-sample-training-and-test-data-from-dictionary/](https://www.geeksforgeeks.org/python-random-sample-training-and-test-data-from-dictionary/)

有时，在使用机器学习算法时，我们会遇到需要随机区分训练和测试数据的问题。这是一个非常常见的问题，对于机器学习领域来说，解决这个问题是可取的。本文讨论了在不使用外部库的情况下解决这个问题的方法。

**方法:使用`keys() + random.randint()` +计算**
这个问题可以通过以上函数的组合来解决。在本文中，我们使用 randint()从使用 key()提取的密钥中执行随机密钥提取任务。执行逻辑计算以获得分离的测试和训练数据。

```
# Python3 code to demonstrate working of 
# Random Sample Training and Test Data
# Using keys() + randint() + computations
import random

# initializing dictionary
test_dict = {'gfg' : 4, 'is' : 12, 'best' : 6, 'for' : 7, 'geeks' : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing ratio
test = 40
training = 60

# Random Sample Training and Test Data
# Using keys() + randint() + computations
key_list = list(test_dict.keys())

test_key_count = int((len(key_list) / 100) * test)
test_keys = [random.choice(key_list) for ele in range(test_key_count)]
train_keys = [ele for ele in key_list if ele not in test_keys]

testing_dict = dict((key, test_dict[key]) for key in test_keys 
                                        if key in test_dict) 
training_dict = dict((key, test_dict[key]) for key in train_keys 
                                        if key in test_dict) 

# printing result 
print("The testing dictionary is : " + str(testing_dict)) 
print("The training dictionary is : " + str(training_dict)) 
```

**Output :**

> 原始字典为:{“is”:12，“gfg”:4，“best”:6，“for”:7，“极客”:10}
> 测试字典为:{“is”:12，“for”:7 }
> 训练字典为:{“gfg”:4，“best”:6，“极客”:10}