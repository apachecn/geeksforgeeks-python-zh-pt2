# Python |在集合

中移除()并丢弃()

> 原文:[https://www.geeksforgeeks.org/python-remove-discard-sets/](https://www.geeksforgeeks.org/python-remove-discard-sets/)

在本文中，我们将看到如何使用 discard()和 remove()方法移除集合中的元素。我们还将了解这两种方法之间的区别，尽管它们产生的结果是相同的。

示例:

```
Input : set = ([10, 20, 26, 41, 54, 20])
Output : {41, 10, 26, 54}

Input : set = (["ram", "aakash", "kaushik", "anand", "prashant"])
Output : {'ram', 'prashant', 'kaushik', 'anand'}

```

**方法 1:使用丢弃()方法**

Python 中的内置方法 discard()仅在集合中存在元素时才从集合中移除该元素。如果元素不在集合中，则不会出现错误或异常，并且会打印原始集合。
如果元素存在于集合中:

```
# Python program to remove random elements of choice
# Function to remove elements using discard()
def Remove(sets):
    sets.discard(20)
    print (sets)

# Driver Code
sets = set([10, 20, 26, 41, 54, 20])
Remove(sets)
```

输出:

```
{41, 10, 26, 54}

```

如果元素不在集合中:

```
# Python program to remove random elements of choice
# Function to remove elements using discard()
def Remove(sets):
    sets.discard(21)
    print (sets)

# Driver Code
sets = set([10, 20, 26, 41, 54, 20])
Remove(sets)
```

输出:

```
{41, 10, 26, 20, 54}

```

**方法二:使用 remove()方法**

Python 中的内置方法 remove()只在元素存在于集合中时从集合中移除元素，就像 discard()方法一样，但是如果元素不存在于集合中，则会引发错误或异常。
如果元素存在于集合中:

```
# Python program to remove random elements of choice
# Function to remove elements using remove()
def Remove(sets):
    sets.remove("aakash")
    print (sets)

# Driver Code
sets = set(["ram", "aakash", "kaushik", "anand", "prashant"])
Remove(sets)
```

输出:

```
{'ram', 'anand', 'prashant', 'kaushik'}

```

如果元素不在集合中:

```
# Python program to remove random elements of choice
# Function to remove elements using remove()
def Remove(sets):
    sets.remove("gaurav")
    print (sets)

# Driver Code
sets = set(["ram", "aakash", "kaushik", "anand", "prashant"])
Remove(sets)
```

输出:

```
No Output

```

错误:

```
Traceback (most recent call last):
  File "/home/bf95b32da22ada77d72062a73d3e0980.py", line 9, in 
    Remove(sets)
  File "/home/bf95b32da22ada77d72062a73d3e0980.py", line 4, in Remove
    sets.remove("gaurav")
KeyError: 'gaurav'
```