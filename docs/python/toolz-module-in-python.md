# Python 中的 Toolz 模块

> 原文:[https://www.geeksforgeeks.org/toolz-module-in-python/](https://www.geeksforgeeks.org/toolz-module-in-python/)

**Toolz** 包为迭代器、函数和字典提供了一组实用函数。这些函数扩展了标准库 **itertools** 和 **functools** ，并大量借用了当代函数式语言的标准库。该包由以下模块组成–

*   听写工具
*   [真菌毒素](#functoolz)
*   [迭代工具](#itertoolz)
*   [食谱](#recipes)
*   沙盒

## dicttoolz

**功能–**

*   **assoc(d, key, value[, factory]) –** Returns a new dict with new key value pair. It does not modify the initial dictionary.

    ```
    import toolz

    d = toolz.dicttoolz.assoc({'Geeks':0}, 'forGeeks', 1)
    print(d)
    ```

    **输出–**

    ```
    {'Geeks': 0, 'forGeeks': 1}

    ```

*   **assoc_in(d, keys, value[, factory]) –** Returns a new dict with new, potentially nested, key value pair

    ```
    import toolz

    d = toolz.dicttoolz.assoc_in({'Geeks':0}, 'forGeeks', 1)
    print(d)
    ```

    **输出–**

    > {'Geeks': 0，' f ':{ ' o ':{ ' r ':{ ' G ':{ ' e ':{ ' e ':{ ' k ':{ ' s ':1 } } } } } }

*   **dissoc(d, *keys) –** Returns a new dict with the given key(s) removed. It does not modify the initial dictionary.

    ```
    import toolz

    d = toolz.dicttoolz.dissoc({'g':0, 'e':1, 
                                'k':2, 's':3},
                                'k', 'e')
    print(d)
    ```

    **输出–**

    ```
    {'g': 0, 's': 3}

    ```

*   **get_in(keys, ds[, default, no_default]) –** Returns ds[I0][I1]…[IX] where [I0, I1, …, IX] are keys and ds is a nested dictionary. If ds[I0][I1]…[IX] cannot be found, it returns “default”.

    ```
    import toolz

    nested_dict ={'d1':{'k1':'v1', 'k2':'v2'}, 
                  'd2':{'k3':{'d2A':{'k4':'v4'}}}}

    d = toolz.dicttoolz.get_in(['d1'], nested_dict)
    print(d)

    d = toolz.dicttoolz.get_in(['d2', 'k3', 'd2A'], 
                               nested_dict)
    print(d)
    ```

    **输出–**

    ```
    {'k1': 'v1', 'k2': 'v2'}
    {'k4': 'v4'}

    ```

*   **itemfilter(predicate, d[, factory]) –** It filters items in dictionary by item.

    ```
    import toolz

    def func(item):

        key, val = item

        return key == ord(val)-65

    d = {0:'A', 1:'B', 3:'C', 5:'F'}
    print(toolz.dicttoolz.itemfilter(func, d))
    ```

    **输出–**

    ```
    {0: 'A', 1: 'B', 5: 'F'}

    ```

*   **itemmap(func, d[, factory]) –** Applies function to items of dictionary.

    ```
    import toolz

    d = {0:'A', 1:'B', 3:'C', 5:'F'}
    print(toolz.dicttoolz.itemmap(reversed, d))
    ```

    **输出–**

    ```
    {'A': 0, 'B': 1, 'C': 3, 'F': 5}

    ```

*   **keyfilter(predicate, d[, factory]) –** It filters items in dictionary by key.

    ```
    import toolz

    def func(key):
        return 5<= len(key)<7

    d = {'python': 0, 'julia': 1, 'java': 3, 'javascript': 5}
    print(toolz.dicttoolz.keyfilter(func, d))
    ```

    **输出–**

    ```
    {'python': 0, 'julia': 1}

    ```

*   **keymap(func, d[, factory] –** Applies function to keys of dictionary .

    ```
    import toolz

    def func(key):
        return ''.join(reversed(key))

    d = {'python': 0, 'julia': 1, 'java': 3, 'javascript': 5}
    print(toolz.dicttoolz.keymap(func, d))
    ```

    **输出–**

    ```
    {'nohtyp': 0, 'ailuj': 1, 'avaj': 3, 'tpircsavaj': 5}

    ```

*   **merge(*dicts, **kwargs) –** It merges a collection of dictionaries.

    ```
    import toolz

    dict1 = {1:1, 2:4}
    dict2 = {3:9, 2:8, 4:16}
    print(toolz.dicttoolz.merge(dict1, dict2))
    ```

    **输出–**

    ```
    {1: 1, 2: 8, 3: 9, 4: 16}

    ```

*   **merge_with(func, *dicts, **kwargs) –** Merges dictionaries and applies function to combined values.

    ```
    import toolz

    dict1 = {1:1, 2:4}
    dict2 = {3:9, 2:8, 1:1}
    print(toolz.dicttoolz.merge_with(sum, dict1, dict2))
    ```

    **输出–**

    ```
    {1: 2, 2: 12, 3: 9}

    ```

*   **update_in(d, keys, func[, default, factory]) –**Updates value in a nested dictionary. If keys = [k0, .., kX] and d[k0, …, kX] = value, update_in returns a copy of the original dictionary with ‘value’ replaced by func(value).

    ```
    import toolz

    def func(value):
        return value//2

    nested_dict = {1:{11:111}, 2:{22:222}}
    print(toolz.dicttoolz.update_in(nested_dict, 
           [1, 11], func))
    ```

    **输出–**

    ```
    {1: {11: 55}, 2: {22: 222}}

    ```

*   **valfilter(predicate, d[, factory]) –** Filter items in dictionary by value.

    ```
    import toolz

    def func(value):
        return 4<len(value)<7

    d = {0: 'python', 1: 'julia', 3: 'java', 5: 'javascript'}
    print(toolz.dicttoolz.valfilter(func, d))
    ```

    **输出–**

    ```
    {0: 'python', 1: 'julia'}

    ```

*   **valmap(func, d[, factory]) –** Apply function to values of dictionary.

    ```
    import toolz

    def func(value):
        return ''.join(reversed(value))

    d = {0: 'python', 1: 'julia', 3: 'java', 5: 'javascript'}
    print(toolz.dicttoolz.valmap(func, d))
    ```

    **输出–**

    ```
    {0: 'nohtyp', 1: 'ailuj', 3: 'avaj', 5: 'tpircsavaj'}

    ```

## functools

**功能–**

*   **apply(*func_and_args, **kwargs) –** It simply applies a function and returns the result.

    ```
    import toolz

    def double(n):
        return n + n

    print(toolz.functoolz.apply(double, 2))
    ```

    **输出–**

    ```
    4

    ```

*   **complement(func) –** As its name suggests, it converts returns the logical complement of the input provided.

    ```
    import toolz

    def is_mulitple_of_5(n):
        return n % 5 == 0

    not_multiple_of_5 = toolz.functoolz.complement(is_mulitple_of_5)

    print(is_mulitple_of_5(10))
    print(not_multiple_of_5(10))
    ```

    **输出–**

    ```
    True
    False

    ```

*   **compose(*funcs) –** It returns a function that applies other functions in sequence. Functions are applied from right to left. If no arguments are provided, the identity function (f(x) = x) is returned.

    ```
    import toolz

    def func(n):
        return n + n

    def square(n):
        return n * n

    x = toolz.functoolz.compose(func, square)(3)
    print(x)
    ```

    **输出–**

    ```
    18

    ```

*   **compose_left(*funcs) –** It returns a function that applies other functions in sequence. Functions are applied from left to right. If no arguments are provided, the identity function (f(x) = x) is returned.

    ```
    import toolz

    def func(n):
        return n + n

    def square(n):
        return n * n

    x = toolz.functoolz.compose_left(func, square)(3)
    print(x)
    ```

    **输出–**

    ```
    36

    ```

*   **flip –** Call the function with the arguments in reverse order.

    ```
    import toolz

    def mod(a, b):
        return a % b

    print('7 % 3 :', toolz.functoolz.flip(mod, 3, 7))
    ```

    **输出–**

    ```
    7 % 3 : 1

    ```

*   **identity(x) –** Identity function, simply returns x.

    ```
    import toolz

    print(toolz.functoolz.identity(6))
    ```

    **输出–**

    ```
    6

    ```

*   **pipe(data, *funcs) –** Pipe a value through a sequence of functions. It is equivalent to compose_left(*funcs)

    ```
    import toolz

    print(toolz.functoolz.pipe(3, double, square))
    ```

    **输出–**

    ```
    36

    ```

*   **thread_first(val, *forms) –** Thread value through a sequence of functions/forms.

    ```
    import toolz

    def mod(a, b):
        return a % b

    def double(n):
        return n + n

    print(toolz.functoolz.thread_first(3, (mod, 2), double))
    ```

    **输出–**

    ```
    2

    ```

*   **thread_last(val, *forms) –** Thread value through a sequence of functions/forms.

    ```
    import toolz

    def mod(a, b):
        return a % b

    def double(n):
        return n + n

    print(toolz.functoolz.thread_last(3, (mod, 2), double))
    ```

    **输出–**

    ```
    4

    ```

## itertools

**功能–**

*   **accumulate(binop, seq[, initial]) –** This is similar to ‘reduce’ function. It repeatedly applies a function to a sequence accumulating results.

    ```
    import toolz
    from operator import add

    print(list(toolz.itertoolz.accumulate(add, [1, 2, 3, 4])))
    ```

    **输出–**

    ```
    [1, 3, 6, 10]

    ```

*   **concat(seqs) –** It concatenates two or more iterables.

    ```
    import toolz

    print(list(toolz.itertoolz.concat([[1], 
                                      ['a'], 
                                      [2, 3, 4]])))
    ```

    **输出–**

    ```
    [1, 'a', 2, 3, 4]

    ```

*   **cons(item, seq) –** It adds ‘item’ in the beginning of sequence. It is equivalent to insert(0, item).

    ```
    import toolz

    print(list(toolz.itertoolz.cons(1, ['a', 'b'])))
    ```

    **输出–**

    ```
    [1, 'a', 'b']

    ```

*   **diff(*seqs, **kwargs) –** It compares the elements at every index in both iterables and returns the list of differing pairs.

    ```
    import toolz

    print(list(toolz.itertoolz.diff([1, 2, 3], [2, 2, 4])))
    ```

    **输出–**

    ```
    [(1, 2), (3, 4)]

    ```

*   **drop(n, seq) –** It drops the first n elements of sequence and returns the new sequence.

    ```
    import toolz

    print(list(toolz.itertoolz.drop(3, [2, 3, 2, 6, 4, 7])))
    ```

    **输出–**

    ```
    [6, 4, 7]

    ```

*   **frequencies(seq) –** It returns a dictionary with elements and their count in sequence. It is equivalent to collections.Counter.

    ```
    import toolz

    print(toolz.itertoolz.frequencies(['c',
                                       'b',
                                       'c', 
                                       'b', 
                                       'd', 
                                       'e', 
                                       'h', 
                                       'h',
                                       'b']))
    ```

    **输出–**

    ```
    {'c': 2, 'b': 3, 'd': 1, 'e': 1, 'h': 2}

    ```

*   **groupby(func, seq) –** It returns a dictionary after grouping the sequence elements according to func.

    ```
    import toolz

    print(toolz.itertoolz.groupby(len, 
                                  ['geeks', 'for', 'geeks']))
    ```

    **输出–**

    ```
    {5: ['geeks', 'geeks'], 3: ['for']}

    ```

*   **isdistinct(seq) –** It returns True if all elements in the sequence are distinct, else False.

    ```
    import toolz

    print(toolz.itertoolz.isdistinct('geeks'))
    ```

    **输出–**

    ```
    False

    ```

*   **不可改变的(x)–**如果 x 是可迭代的，则返回真，否则返回假。

    ```
    print(toolz.itertoolz.isiterable([10]))
    ```

    ```
    Output - True

    ```

*   **interleave(seqs) –** It interleaves the sequences, i.e. concatenates the sequences index-wise.

    ```
    import toolz

    print(list(toolz.itertoolz.interleave([[10, 20], 
                                           [5, 8, 11]])))
    ```

    **输出–**

    ```
    [10, 5, 20, 8, 11]

    ```

*   **topk(k, seq[, key]) –** It returns the top k largest elements of the sequence.

    ```
    import toolz

    print(list(toolz.itertoolz.topk(2,
                                    [10, 20, 5, 8, 11])))
    ```

    **输出–**

    ```
    [20, 11]

    ```

*   **unique(seq[, key]) –** It returns the distinct elements of sequence just like set(seq).

    ```
    import toolz

    print(list(toolz.itertoolz.unique([10,
                                       20,
                                       5,
                                       8, 
                                       10,
                                       20])))
    ```

    **输出–**

    ```
    [10, 20, 5, 8]

    ```

*   **merge_sorted(*seqs, **kwargs) –** It merges sorted iterables in such a way that the resulting collection is also sorted.

    ```
    import toolz

    print(list(toolz.itertoolz.merge_sorted([5, 10, 20], 
                                            [4, 12, 24])))
    ```

    **输出–**

    ```
    [4, 5, 10, 12, 20, 24]

    ```

*   **mapcat(func, seqs) –** It applies func to each sequence and concatenates the results.

    ```
    import toolz

    print(list(toolz.itertoolz.mapcat(lambda iter: [e * 2 for e in iter], 
                                      [[5, 10, 20], 
                                       [4, 12, 24]])))
    ```

    **输出–**

    ```
    [10, 20, 40, 8, 24, 48]

    ```

*   **remove(predicate, seq) –** It returns those elements from sequence for which predicate is False. It is complement function of filter.

    ```
    import toolz

    print(list(toolz.itertoolz.remove(lambda x: x % 2 == 0,
                                      [5, 21, 4, 12, 24])))
    ```

    **输出–**

    ```
    [5, 21]

    ```

## 方法

**功能–**

*   **countby(key, seq) –** Count elements of a collection by a key function.

    ```
    import toolz

    def iseven(n):
        return n % 2 == 0

    print(toolz.recipes.countby(iseven, [12, 123, 1234]))
    ```

    **输出–**

    ```
    {True: 2, False: 1}

    ```

*   **partitionby(func, seq) –** Partition a sequence according to a given function.

    ```
    import toolz

    def iseven(n):
        return n % 2 == 0

    print(list(toolz.recipes.partitionby(iseven, 
                                         [12, 123,  
                                          31, 1234])))
    ```

    **输出–**

    ```
    [(12, ), (123, 31), (1234, )]

    ```

## 沙箱

**功能–**

*   **parallel.fold(binop, seq[, default, map, …] –** Reduce without guarantee of ordered reduction.

    ```
    import toolz

    def sum(a, b):
        return a + b

    print(toolz.sandbox.parallel.fold(sum, [1, 2, 3, 4]))
    ```

    **输出–**

    ```
    10
    ```

*   **core.unzip(seq) –** Inverse of zip.

    ```
    import toolz

    l1, l2 = toolz.sandbox.core.unzip([(0, 1),
                                       (1, 2),
                                       (2, 3)])

    print(list(l1), list(l2))
    ```

    **输出–**

    ```
    [0, 1, 2] [1, 2, 3]

    ```