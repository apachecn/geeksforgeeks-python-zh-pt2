# Python 中搁置类的子类和方法

> 原文:[https://www . geesforgeks . org/subclass-and-of-of-shelf-class-in-python/](https://www.geeksforgeeks.org/subclass-and-methods-of-shelve-class-in-python/)

搁置是 Python 标准库中的一个模块，可以用作非关系数据库。dbm 和 while 的主要区别在于，while 可以将其值作为任意对象，这些对象可以由 [*pickle 模块*](https://www.geeksforgeeks.org/pickle-python-object-serialization/) 处理，而在 dbm 数据库中，我们只能使用 Python 的标准数据类型作为其数据库值。搁置中的键始终是一个字符串对象，而值可以是任意 pickle 对象。

在本文中，我们将看一下搁置的子类和可以用来处理“搁置”对象的内置方法。请通过[*这篇文章了解从货架对象中检索*](https://www.geeksforgeeks.org/retrieving-and-updating-data-contained-in-shelve-in-python/) (插入、更新、检索)数据的基本情况。

#### 以下是搁置的三个子类:

<figure class="table">

| **类名** | **描述** |
| 架子 | 这是 shelve 的基类，它将 dict 对象和字符串对象中的腌制对象值存储为键。 |
| BsdDbShelf | 传递给这个子类 dict 对象的 pickle 对象必须支持这些函数:next()、previous()，

first()，last()和 set_location(key)，这些在 pybsddb(第三方模块)中可用，但在中不可用其他数据库模块。 |
| DbfilenameShelf 搁板 | 这也是一个搁置的基类，它接受文件名作为参数，而不是像其他对象一样接受 dict 对象。默认情况下，它使用 dbm.open()打开文件进行读写。 |

</figure>

**示例:**

## 蟒蛇 3

```
# In this example we will see
# the different types of objects
# of sub class of shelve class
import shelve

# importing bsddb module to create
# a bsddb object which can support
# mentioned next(), first() methods..
import bsddb

# Shelve Class :
d = {1 : 'geeks', 2 : 'GfG'}

# Dictionary object as parameter
Shelf_obj = shelve.Shelf(d)

print(type(Shelf_obj))

# BsdDbShelf Class :
bsddb_file = bsddb.btopen('spam.db', 'c')

# bsddb object as parameter
bsddb_obj = shelve.BsdDbShelf(bsddb_file)

print(type(bsddb_obj))

# DbfilenameShelf Class :
# File name as parameter
Dbfile_obj = shelve.open('file_name', writeback = True)

print(type(Dbfile_obj))
```

**输出:**

```
<class 'shelve.Shelf'>
<class 'shelve.BsdDbShelf'>
<class 'shelve.DbfilenameShelf'>
```

### **类搁置。架(dict，协议=无，写回=假，密钥编码= ' utf-8 '**)**:**

***collections . ABC . MultipleMapping***的一个子类，将 pickle 值存储为字典对象。

*   默认情况下，使用 pickle 版本 3 协议，如果使用任何其他协议，则在构造函数的协议参数中指定。
*   如果写回参数设置为真，盘架会将所有条目保存为缓存，并在同步或关闭时将其释放回字典。但是它将使用更多的内存，因此同步和关闭可能需要更长的时间。
*   keyencoding 参数在将关键字赋予字典对象之前，用于编码关键字的编码类型。

#### 以下是为此类定义的方法:

<figure class="table">

| **方法** | **描述** |
| ***货架。__ 包含 _ _(关键)*** | 返回一个布尔类对象，如果参数中给定的键出现在可折叠字典中，则返回 True否则，对象返回 False。 |
| ***货架。__ 德尔 __()*** | 从磁盘中删除盘架字典对象。 |
| ***货架。__getitem__(关键)*** | 返回 dict 对象中对应于给定键的相应值作为参数。 |
| ***货架。__len__()*** | 返回字典中存在的项目总数。 |
| ***货架。__delitem__(关键)*** | 从字典中删除与作为参数给定的键对应的特定项。 |
| ***货架。__setitem__(键，值)*** | 此方法用于将字典中的现有项更新为新值对应于作为参数给定的键到也作为第二参数给定的新值。 |
| ***货架获取(键，默认=无)*** | 此方法将返回与作为参数给出的键相对应的值(如果存在)否则返回作为第二个参数给定的值，该值被默认设置为无。

 |
| ***货架。__iter__()*** | 返回字典对象的迭代器。 |
|  | 关闭当前打开的盘架对象文件。 |
|  | 不删除字典对象，而是删除所有存在的项目让它变空。 |
| ***货架弹出(键，默认= 'KeyError')*** | 移除对应于给定键参数的项并返回键值，如果存在，则返回给定的第二个参数引发密钥错误。 |
|  | 从 dict 中移除并返回一些(键、值)对作为元组，否则会引发键错误如果 dict 对象为空。 |
| ***搁板设置默认值(键，默认值=无)*** | 将第二个参数设置为第一个参数中键的值，如果键为，还将设置 D[key] = dD 中不存在，或默认为无。 |
| ***货架物品()*** | 返回字典对象中所有项的键值对的二元组列表。 |
|  | 包含对象键的迭代器。 |
|  | 对象中包含值的迭代器。 |

</figure>

当我们在一个简单的字典对象上执行操作时，上述方法可以很容易地实现。