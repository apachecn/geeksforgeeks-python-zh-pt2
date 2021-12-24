# Python 程序求一个列表的累计和

> 原文:[https://www . geesforgeks . org/python-program-to-find-累计列表总和/](https://www.geeksforgeeks.org/python-program-to-find-cumulative-sum-of-a-list/)

问题语句要求生成一个新列表，其 i^{th}元素等于(i + 1)个元素的总和。

**例:**

```py
Input : list = [10, 20, 30, 40, 50]
Output : [10, 30, 60, 100, 150]

Input : list = [4, 10, 15, 18, 20]
Output : [4, 14, 29, 47, 67]

```

**方法 1 :**
我们将使用列表理解和列表切片的概念来获得列表的累积和。列表理解被用来访问列表中的每个元素，切片被用来从开始访问 i+1 元素。我们使用 sum()方法将列表中的元素从开始到 i+1 进行求和。
以下是上述办法的实施:

## 蟒蛇 3

```py
# Python code to get the Cumulative sum of a list
def Cumulative(lists):
    cu_list = []
    length = len(lists)
    cu_list = [sum(lists[0:x:1]) for x in range(0, length+1)]
    return cu_list[1:]

# Driver Code
lists = [10, 20, 30, 40, 50]
print (Cumulative(lists))
```

**输出:**

```py
[10, 30, 60, 100, 150]

```

**进场 2:**

## 蟒蛇 3

```py
list=[10,20,30,40,50]
new_list=[]
j=0
for i in range(0,len(list)):
    j+=list[i]
    new_list.append(j)

print(new_list)
#code given by Divyanshu singh
```

**输出:**

```py
[10, 30, 60, 100, 150]

```