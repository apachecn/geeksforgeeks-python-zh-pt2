# Python |按键或值对 Python 词典进行排序

> 原文:[https://www . geesforgeks . org/python-sort-python-dictionary-by-key-or-value/](https://www.geeksforgeeks.org/python-sort-python-dictionaries-by-key-or-value/)

**先决条件:**

*   [词典](https://www.geeksforgeeks.org/python-dictionary/)
*   [列表](https://www.geeksforgeeks.org/list-methods-python/)
*   [合并两本词典](https://www.geeksforgeeks.org/python-merging-two-dictionaries/)
*   [词典方法](https://www.geeksforgeeks.org/dictionary-methods-in-python-set-1-cmp-len-items/)

**问题陈述–以下是需要执行的主要任务。**

1.  创建一个字典，并按字母顺序显示其关键字。
2.  显示按键的字母顺序排序的键和值。
3.  与第(ii)部分相同，但按值的字母顺序排序。

**方法–**
加载字典并执行以下操作:

1.  首先，使用 *key_value.iterkeys()* 函数对按键进行字母排序。
2.  其次，使用*排序(key_value)* 功能&按字母顺序排序按键，打印对应的值。
3.  第三，使用*key _ value . item()，key = lambda (k，v) : (v，k))* 对值进行字母排序

让我们尝试执行上述任务:

1.  按字母顺序显示按键:
    **示例:**

```
Input:
key_value[2] = '64'       
key_value[1] = '69'
key_value[4] = '23'
key_value[5] = '65'
key_value[6] = '34'
key_value[3] = '76'

Output:
1 2 3 4 5 6 
```

1.  **节目:**

## 蟒蛇 3

```
# Function calling
def dictionairy():
 # Declare hash function     
 key_value ={}   

# Initializing value
 key_value[2] = 56      
 key_value[1] = 2
 key_value[5] = 12
 key_value[4] = 24
 key_value[6] = 18     
 key_value[3] = 323

 print ("Task 1:-\n")
 print ("Keys are")

 # iterkeys() returns an iterator over the
 # dictionary’s keys.
 for i in sorted (key_value.keys()) :
     print(i, end = " ")

def main():
    # function calling
    dictionairy()            

# Main function calling
if __name__=="__main__":     
    main()
```

**Output:** 

```
Task 1:-

Keys are
1 2 3 4 5 6
```

2.  使用键按字母顺序对键和值进行排序。
    **例:**

```
Input:
key_value[2] = '64'       
key_value[1] = '69'
key_value[4] = '23'
key_value[5] = '65'
key_value[6] = '34'
key_value[3] = '76'

Output:
(1, 69) (2, 64) (3, 76) (4, 23) (5, 65) (6, 34)
```

1.  **节目:**

## 蟒蛇 3

```
# function calling
def dictionairy():

 # Declaring the hash function     
 key_value ={}   

# Initialize value
 key_value[2] = 56      
 key_value[1] = 2
 key_value[5] = 12
 key_value[4] = 24
 key_value[6] = 18     
 key_value[3] = 323

 print ("Task 2:-\nKeys and Values sorted in",
            "alphabetical order by the key  ") 

 # sorted(key_value) returns an iterator over the
 # Dictionary’s value sorted in keys. 
 for i in sorted (key_value) :
    print ((i, key_value[i]), end =" ")

def main():
    # function calling
    dictionairy()            

# main function calling
if __name__=="__main__":    
    main()
```

**Output:** 

```
Task 2:-
Keys and Values sorted in alphabetical order by the key  
(1, 2) (2, 56) (3, 323) (4, 24) (5, 12) (6, 18)
```

2.  使用值
    **按字母顺序对键和值进行排序示例:**

```
Input:
key_value[2] = '64'       
key_value[1] = '69'
key_value[4] = '23'
key_value[5] = '65'
key_value[6] = '34'
key_value[3] = '76'

Output:
(4, 23), (6, 34), (2, 64), (5, 65), (1, 69), (3, 76)
```

1.  **节目:**

## 蟒蛇 3

```
# Function calling
def dictionairy():

 # Declaring hash function     
 key_value ={}   

# Initializing the value
 key_value[2] = 56      
 key_value[1] = 2
 key_value[5] = 12
 key_value[4] = 24
 key_value[6] = 18     
 key_value[3] = 323

 print ("Task 3:-\nKeys and Values sorted",
   "in alphabetical order by the value")

 # Note that it will sort in lexicographical order
 # For mathematical way, change it to float
 print(sorted(key_value.items(), key =
             lambda kv:(kv[1], kv[0])))   

def main():
    # function calling
    dictionairy()           

# main function calling
if __name__=="__main__":     
    main()
```

**Output:** 

```
Task 3:-
Keys and Values sorted in alphabetical order by the value
[(1, 2), (5, 12), (6, 18), (4, 24), (2, 56), (3, 323)]
```

**按键排序字典**
**注:**将按字典顺序排序
以键的类型为字符串
**程序:**

## 蟒蛇 3

```
# Creates a sorted dictionary (sorted by key)
from collections import OrderedDict

dict = {'ravi':'10','rajnish':'9','sanjeev':'15','yash':'2','suraj':'32'}
dict1 = OrderedDict(sorted(dict.items()))
print(dict1)
```

这里，输出是按字典顺序使用关键字排序的字典
**字典顺序:**https://en.wikipedia.org/wiki/Lexicographical_order
**学习结果:**

*   如何处理字典？
*   字典的搜索时间复杂度为 0(1)，而列表的搜索时间复杂度为 0(n)。所以建议尽可能使用字典。
*   词典的最佳应用可以在*推特情感分析*中看到，在这里使用词典方法分析推特情感。