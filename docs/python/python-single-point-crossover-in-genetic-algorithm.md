# Python |遗传算法中的单点交叉

> 原文:[https://www . geesforgeks . org/python-遗传算法单点交叉/](https://www.geeksforgeeks.org/python-single-point-crossover-in-genetic-algorithm/)

**遗传算法中的单点交叉**是一种交叉形式，其中选择双亲染色体并选择随机/给定点，例如在给定/选择点之后基因/数据在它们之间互换

**例:**

```
P1: 000011110011 
P2: 101010101010

Point: 4
After Crossover:
C1: 000010101010
C2: 101011110011

```

问题是为两个给定父母的交叉选择一个随机点，并从给定的一对染色体中产生至少五代孩子。

**代码:遗传算法中单点交叉的 Python 程序**

```
# library to generate a random number
import random

# function for implementing the single-point crossover
def crossover(l, q):

# converting the string to list for performing the crossover
    l = list(l)
    q = list(q)

# generating the random number to perform crossover
    k = random.randint(0, 15)
    print("Crossover point :", k)

# interchanging the genes
    for i in range(k, len(s)):
        l[i], q[i] = q[i], l[i]
    l = ''.join(l)
    q = ''.join(q)
    print(l)
    print(q, "\n\n")
    return l, q

# patent chromosomes:

s = '1100110110110011'
p = '1000110011011111'
print("Parents")
print("P1 :", s)
print("P2 :", p, "\n")

# function calling and storing the off springs for 
# next generation crossover
for i in range(5):
    print("Generation ", i+1, "Childrens :")
    s, p = crossover(s, p)
```

**输出:**

```
Parents
P1 : 1100110110110011
P2 : 1000110011011111 

Generation  1 Childrens :
Crossover point : 2
1100110011011111
1000110110110011 

Generation  2 Childrens :
Crossover point : 7
1100110110110011
1000110011011111 

Generation  3 Childrens :
Crossover point : 0
1000110011011111
1100110110110011 

Generation  4 Childrens :
Crossover point : 7
1000110110110011
1100110011011111 

Generation  5 Childrens :
Crossover point : 2
1000110011011111
1100110110110011

```