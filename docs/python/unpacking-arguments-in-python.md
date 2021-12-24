# 在 Python 中解包参数

> 原文:[https://www . geesforgeks . org/拆包-python 中的参数/](https://www.geeksforgeeks.org/unpacking-arguments-in-python/)

如果你现在已经使用 Python 几天了，你可能知道解包元组。对于初学者来说，你可以解包元组或列表来分离变量，但不是这样。Python 中还有很多东西需要解释。

**解包而不存储值:**您可能会遇到这样的情况，您可能不需要元组中的所有值，但您只想存储其中的一些值。在这种情况下，您可以使用 *_* 来忽略某些值。现在，让我们将其与上面的*实现结合起来

**例 1:**

## 蟒蛇 3

```
# unpacking python tuple using _ 

# first and last value will be ignored 
# and won't be stored second will be 
# assigned to b and remaining will be
# assigned to x 
_, b, *x, _ = ("I ", "love ", "Geeks ",
               "for ", "Geeks ", 3000) 

# print details 
print(b)
print(x) 
```

**输出:**

```
love 
['Geeks ', 'for ', 'Geeks ']

```

**说明:**

请注意，这里第一个和最后一个变量设置为下划线(_)。在 python 中，下划线用于忽略值或丢弃变量，这意味着不会存储“I”和 3000。

**例 2:**

## 蟒 3

```
# unpacking python tuple using _* 

# first second and last value will be stored
# remaining will be ignored by using *_
a, b, *_, c = ("I ", "love ", "Geeks ",
               "for ", "Geeks ", 3000) 

# print details 
print(a)
print(b) 
print(c)
```

**输出:**

```
I 
love 
3000

```

**说明:**

注意这里在 **a** 和 **b** 中，第一个和第二个值被赋值，在 **c** 中，最后一个值被赋值。那么，第三个、第四个和第五个呢？嗯，它们只是被忽略了，因为我们使用了 ***_** 。如果我们对一个变量使用*的话，那么所有这些都将作为一个列表进入这个变量。因为我们使用了 _ 而不是变量，所以整个单词列表被完全忽略了。

**示例 3:** 这里的想法是创建一个函数，该函数将接受一个数字列表，并在列表中返回其总和、平均值、最大值和最小值。然后，我们将重用该函数，以获得不同用例所需的功能。

## 蟒 3

```
def arithmetic_operations(arr: list):
  MAX = max(arr)
  MIN = min(arr)
  SUM = sum(arr)
  AVG = SUM/len(arr)

  return (SUM, AVG, MAX, MIN)

if __name__ == '__main__':
  arr = [5, 8, 9, 12, 50, 3, 1]

  # for all data
  sum_arr, avg_arr, max_arr, min_arr = arithmetic_operations(arr)
  print("CASE 1 ", sum_arr, avg_arr, max_arr, min_arr)

  #for only avg and max
  _, avg_arr, max_arr, _ = arithmetic_operations(arr)
  print("CASE 2 ", avg_arr, max_arr)

  # for only sum and min
  sum_arr, *_, min_arr = arithmetic_operations(arr)
  print("CASE 3 ", sum_arr, min_arr)
```

**输出:**

```
CASE 1  88 12.571428571428571 50 1
CASE 2  12.571428571428571 50
CASE 3  88 1

```

上面的代码是为了演示如何让一个函数返回多个值，但一次只使用必要的值，而不浪费内存。