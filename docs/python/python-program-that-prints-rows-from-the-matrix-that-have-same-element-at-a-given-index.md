# 打印矩阵中给定索引处具有相同元素的行的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-从给定索引处具有相同元素的矩阵中打印行的程序/](https://www.geeksforgeeks.org/python-program-that-prints-rows-from-the-matrix-that-have-same-element-at-a-given-index/)

给定一个矩阵，下面的文章展示了如何提取在指定索引处具有相似数字的行并作为输出返回。

> **输入** : test_list = [[3345，6355，83，938]，[323，923，845]，[192，993，49]，[98，34，23]]，K = 1
> **输出** : [[3345，6355，83，938]，[192，993，49]]
> **解释** : 3
> **输入** : test_list = [[3445，6355，83，938]，[323，923，845]，[192，993，49]，[98，34，23]]，K = 1
> **输出** : [[192，993，49]]
> **解释**:第 1 列 9。

**方法 1 :** *使用全部()和*[T5】列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用 all()检查指定索引处的所有数字，列表理解用于迭代每一行。

## 蟒蛇 3

```
# initializing list
test_list = [[3345, 6355, 83, 938], [
    323, 923, 845], [192, 993, 49], [98, 34, 23]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

# checking for all elements match using all()
res = [row for row in test_list if all(
    str(i)[K] == str(row[0])[K] for i in row)]

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原来的名单是:[[3345，6355，83，938]，[323，923，845]，[192，993，49]，[98，34，23]]
> 
> 筛选的行:[[3345，6355，83，938]，[192，993，49]]

**方法二:** *使用* [*滤镜()*](https://www.geeksforgeeks.org/filter-in-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*和 all()**

*在本例中，我们使用 filter()和 lambda 函数来检查所有行中相似的 K 列数字。与上述方法类似，all()执行检查每个元素的任务。*

## *蟒蛇 3*

```
*# initializing list
test_list = [[3345, 6355, 83, 938], [
    323, 923, 845], [192, 993, 49], [98, 34, 23]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

# checking for all elements match using all()
# filter() and lambda function performing filtering
res = list(filter(lambda row: all(
    str(i)[K] == str(row[0])[K] for i in row), test_list))

# printing result
print("Filtered Rows : " + str(res))*
```

***输出:***

> *原来的名单是:[[3345，6355，83，938]，[323，923，845]，[192，993，49]，[98，34，23]]*
> 
> *筛选的行:[[3345，6355，83，938]，[192，993，49]]*