# 什么是 h 股指数？

> 原文:[https://www.geeksforgeeks.org/what-is-h-index/](https://www.geeksforgeeks.org/what-is-h-index/)

**什么是 H–指数？**“H”代表美国好施集团指数，由美国好施集团于 2005 年提出。h 指数被定义为作者级别的指标，试图衡量科学家或学者的出版物的生产率和引用影响。

需要考虑两个参数–

1.  **数量**–纸张数量
2.  **质量**–引用次数

基本上，H 指数是最大的数字，这样一些出版物至少有相同的引用次数。作为表征研究者科学产出的有用指标。

**计算 H 指数–**

例如，假设一位研究员总共发表了 10 篇论文。

<figure class="table">

| **研究论文** | **引用次数** |
| one |         50 |
|           2 |         40 |
| three |         33 |
| four |         23 |
| five |         12 |
| six |         11 |
| seven | eight |
| eight | five |
| nine | one |
|          10 |          0 |

</figure>

> h 指数总是< =发表的论文总数

为了方便起见，让我们按降序排列引文的数量。

H-index 不能是 10，因为至少要有 10 篇研究论文被引用 10 次或 10 次以上。同样的，

H-index 不能为 9，
H-index 不能为 8，
H-index 为 7，因为有 7 篇研究论文有 7 次或 7 次以上的引用。

**示例:**

```py
Input : Citations = [7, 6, 5, 4, 3]
Output : 4
Explanation : There are 5 papers in total. 
              Since the researcher has 4 papers with at least 4 citations each 
              and the remaining one paper has less than 4 citations. 
              So H-index is 4.

```

**寻找 h 股指数的方法:**

1.  按升序或降序对引文数组进行排序。
2.  从最低的纸迭代到最高的纸。
3.  剩余论文(结果)是满足 H 指数条件的论文数。

```py
# calculating H-Index
def H_index(citations):

    # sorting in ascending order
    citations.sort()

    # iterating over the list
    for i, cited in enumerate(citations):

        # finding current result
        result = len(citations) - i

        # if result is less than or equal
        # to cited then return result
        if result <= cited:
            return result

    return 0

# creating the citations
citation = [50, 40, 33, 23, 12, 11, 8, 5, 1, 0]

# calling the function
print(H_index(citation))
```

**输出**

```py
7
```

**时间复杂度:**O(nlogn+n)
T3】空间复杂度: O(1)

**h 股指数的限制:**

1.  不同领域的研究者可以有不同的引用行为。
2.  我们无法比较两个领域不同、研究经验差距巨大的研究者。与经验不足研究员相比，经验丰富的研究员将具有较高的 H 指数。
3.  H-index 值取决于您使用的数据库，它可能因不同的平台而异。