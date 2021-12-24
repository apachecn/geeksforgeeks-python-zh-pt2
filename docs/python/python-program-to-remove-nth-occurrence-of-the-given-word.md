# Python 程序删除给定单词的第 n 次出现

> 原文:[https://www . geeksforgeeks . org/python-给定单词的第 n 次出现程序删除/](https://www.geeksforgeeks.org/python-program-to-remove-nth-occurrence-of-the-given-word/)

给定 Python 中的单词列表，任务是移除列表中给定单词的第 N 个<sup>出现。
**例:**</sup> 

```
Input: list - ["geeks", "for", "geeks"]
       word = geeks, N = 2
Output: list - ["geeks", "for"]

Input: list - ["can", "you",  "can", "a", "can" "?"]
       word = can, N = 1
Output: list - ["you",  "can", "a", "can" "?"]
```

**接近#1:** 采取另一个名单。
列个新单子，说*新列表*。迭代列表中的元素，检查要删除的单词是否与元素和出现次数匹配，否则，将元素追加到*新列表*中。

## 蟒蛇 3

```
# Python3 program to remove Nth
# occurrence of the given word

# Function to remove Ith word
def RemoveIthWord(lst, word, N):
    newList = []
    count = 0

    # iterate the elements
    for i in lst:
        if(i == word):
            count = count + 1
            if(count != N):
                newList.append(i)
        else:
            newList.append(i)

    lst = newList

    if count == 0:
        print("Item not found")
    else:
        print("Updated list is: ", lst)   

    return newList

# Driver code
list = ["geeks", "for", "geeks"]
word = "geeks"
N = 2

RemoveIthWord(list, word, N)
```

**输出:**

```
Updated list is:  ['geeks', 'for']
```

**方法 2:** 从列表中删除。
不制作新的列表，而是从列表本身中删除匹配的元素。迭代列表中的元素，检查要删除的单词是否与元素和出现次数匹配，如果匹配，则删除该项并返回 true。如果返回“真”，则打印列表，否则打印“未找到项目”。

## 蟒蛇 3

```
# Python3 program to remove Nth
# occurrence of the given word

# Function to remove Ith word
def RemoveIthWord(list, word, N):
    count = 0

    for i in range(0, len(list)):
        if (list[i] == word):
            count = count + 1

            if(count == N):
                del(list[i])
                return True

    return False

# Driver code
list = ['geeks', 'for', 'geeks']
word = 'geeks'
N = 2

flag = RemoveIthWord(list, word, N)

if (flag == True):
    print("Updated list is: ", list)
else:
    print("Item not Updated")
```

**输出:**

```
Updated list is:  ['geeks', 'for']
```

**方法#3:** 使用 **pop()** 从列表中删除。
我们可以使用 pop()从列表中弹出匹配的元素，而不是创建一个新的列表并使用 if/else 语句。我们需要使用一个额外的计数器来跟踪索引。
为什么我们需要指数？因为 pop()需要索引才能传入，即 pop(索引)。

## 蟒蛇 3

```
# Python3 program to remove Nth
# occurrence of the given word

# Function to remove nth word
def omit(list1,word,n1):

    # for counting the occurrence of word
    count=0

    # for counting the index number
    # where we are at present            
    index=0  

    for i in list1:
        index+=1
        if i==word:
            count+=1
            if count==n1:

                # (index-1) because in list
                # indexing start from 0th position
                list1.pop(index-1) 
    return list1

# Driver code
list1 = ["he", "is", "ankit", "is",
         "raj", "is","ankit raj"]

word="is"
n1=3

print("new list is :",omit(list1,word,n1))
```

**输出:**

```
new list is : ['he', 'is', 'ankit', 'is', 'raj', 'ankit raj']
```