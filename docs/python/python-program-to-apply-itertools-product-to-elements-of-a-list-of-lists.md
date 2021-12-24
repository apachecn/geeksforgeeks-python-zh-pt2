# 将 itertools.product 应用于列表元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到应用-ITER tools-产品到列表元素/](https://www.geeksforgeeks.org/python-program-to-apply-itertools-product-to-elements-of-a-list-of-lists/)

[Itertools](https://www.geeksforgeeks.org/python-itertools/) 是一个模块，由应用各种基于迭代的操作的方法组成，包括组合、置换等。，关于 Python 中的可迭代组件。它有一套轻量级、内存高效且快速的工具来执行**迭代器代数**。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

### itertools . product()

它用于在列表内或列表间执行笛卡尔乘积。嵌套循环的循环方式是最右边的元素在每次迭代中前进。这种模式创建了一个字典顺序，因此如果输入的 iterables 被排序，那么乘积元组也是按排序顺序的。

它以 iterables 为参数。下面的例子展示了`itertools.product()`方法的一个非常简单的表示。这里它被用作笛卡尔乘积的创造。

**示例:**

```
import itertools

def product(str1, str2):

    # returning the list containing 
    # cartesian product
    return [x for x in itertools.product(list(str1),
                                         list(str2))]

print(product("GfG", "GFG"))
```

**输出:**

> [('G '，' G ')，(' G '，' F '，(' G '，' G ')，(' F '，' G ')，(' F '，' F '，(' F '，' G ')，(' G '，' G ')，(' G '，' G')]

**在列表列表上操作**

要在列表上使用`itertools.product()`方法，请先执行解包操作。这可以通过两种方式实现:

*   **By unpacking the list inside function**

    下面的示例显示了如何通过方法中的简单操作来执行解包。

    ```
    import itertools

    def product(list_of_str):

        str1 = list_of_str[0]
        str2 = list_of_str[1]

        # returning the list 
        # containing cartesian product
        return [x for x in itertools.product(list(str1),
                                             list(str2))]

    print(product(["GfG", "GFG"]))
    ```

    **输出**

    > [('G '，' G ')，(' G '，' F '，(' G '，' G ')，(' F '，' G ')，(' F '，' F '，(' F '，' G ')，(' G '，' G ')，(' G '，' G')]

    这种方式的缺点是，需要知道额外的信息，即列表中列表的长度。

*   **Using ‘*’ operator**

    为了克服上述缺点，使用“*”来解包列表中的列表。因此，上面的代码可以优化如下:

    ```
    import itertools

    def product(lst):

        # Unpack operation performed
        # by '*' operator and returning
        # the list containing cartesian
        # product
        return [x for x in itertools.product(*lst)]

    # list of lists being passed in the method
    print(product(["GfG", "GFG"]))
    ```

    **输出**

    > [('G '，' G ')，(' G '，' F '，(' G '，' G ')，(' F '，' G ')，(' F '，' F '，(' F '，' G ')，(' G '，' G ')，(' G '，' G')]