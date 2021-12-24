# Python 中的弱引用

> 原文:[https://www.geeksforgeeks.org/weak-references-in-python/](https://www.geeksforgeeks.org/weak-references-in-python/)

在 Python 中，我们从来不需要考虑内存管理，因为它是自动完成的。引用计数是 python 中用于检查是否应该进行[垃圾收集](https://www.geeksforgeeks.org/garbage-collection-python/)的计数。因此，幕后发生的事情是，垃圾收集器释放不再需要的内存，这是通过查看引用计数发现的。

由于 Python 中的所有内容都是一个对象，所以如果一个对象被另一个对象引用，那么它就有非零计数，并且不能被垃圾收集(如果不是手动执行的话)。

下面是一个简短的例子，说明如何在 python 中找到任何对象的引用计数。

## 蟒蛇 3

```py
import ctypes

# list object which is referenced by
# my_list
my_list = [1, 2, 3]

# finding the id of list object
my_list_address = id(my_list)

# finds reference count of my_list
ref_count = ctypes.c_long.from_address(my_list_address).value

print(f"Reference count for my_list is: {ref_count}")
```

**输出:**

```py
Reference count for my_list is: 1
```

那么，现在我们已经清楚了引用和垃圾收集的基础，让我们来看看什么是弱引用，为什么我们需要它们？

## 什么是弱引用？

与我们上面讨论的引用**不同，** a **弱引用**是一个不保护对象不被垃圾收集的引用。为什么我们一开始就想要这样的东西？

弱引用有两个主要应用:

*   实现大型对象的缓存(弱字典)。
*   从循环引用中减少痛苦。

为了创建弱引用，Python 为我们提供了一个名为 **weakref** 的模块。在使用 weakref 之前需要记住的一点是，一些内置函数，如 tuple 或 int 不支持这一点。*列表*和*字典*支持是任意一个，但是我们可以通过*子类增加支持。*我们来详细讨论一下应用。

## Weakref 模块

有时，一个大对象存储在缓存中，因此不需要保持它的活动状态。假设您有大量的图像对象，它们被用作映射到图像的键，因此这些对象将保持活动状态。

幸运的是，*weakreverf*模块提供了一种称为 ***WeakKeyDictionary** 和**weakevaluedicationary***的东西，当对象出现在映射对象中时，它们不会保持活动状态。

以下类和方法由 *weakref* 模块提供:

*   **类 weakref.ref(对象[，回调])**–这将返回对*对象的弱引用。*
*   **weakref . proxy(*****object*****【、** ***回调*****)–**这将一个代理返回给使用弱引用的 *object* 。
*   **weakerf . getweakerfcount(*****对象*****)**–返回引用*对象*的弱引用和代理的数量。
*   **weakerf . getweakerf(*****对象*****)**–返回引用*对象的所有弱引用和代理对象的列表。*

让我们通过一些例子来了解工作:

**例 1:**

在下面给出的示例中，我们创建了普通列表对象、弱引用列表对象和代理列表对象，并打印了所有这些对象的弱引用计数。

## 蟒蛇 3

```py
# importing weakref module
import weakref

# creating a class
class GFG(list):
    pass

# creating object of a class
obj = GFG("Geeks")

# creating a normal list object
normal_list = obj
print(f"This is a normal object: {normal_list}")

# this returns a weak reference to obj
weak_list = weakref.ref(obj)
weak_list_obj = weak_list()
print(f"This is a object created using weak reference: {weak_list_obj}")

# creating a proxy of original object
proxy_list = weakref.proxy(obj)
print(f"This is a proxy object: {proxy_list}")

# printing the count of weak references
for objects in [normal_list, weak_list_obj, proxy_list]:
    print(f"Number of weak references: {weakref.getweakrefcount(objects)}")
```

**输出:**

> 这是一个普通对象:['G '，' e '，' e '，' k '，' s']
> 这是一个使用弱引用创建的对象:['G '，' e '，' e '，' k '，' s']
> 这是一个代理对象:['G '，' e '，' e '，' k '，' s']
> 弱引用数:2
> 弱引用数:2
> 弱引用数:0

由于普通对象有对弱引用对象的引用，因此它们都有 2 的弱引用计数，但是由于 proxy_object 是从弱引用创建的代理，因此它没有引用计数。

**例 2:**

在这个例子中，我们将看到如何使用我们在本文前面讨论过的*weakvalueedicationary*。

## 蟒蛇 3

```py
# import weakref module
import weakref

# creates a class
class GFG:

    def __init__(self,data):
        self.data = data

    def __repr__(self):
        return str(self.data)

# creates an object of class GFG
# (consider that this object is very 
# large and has been stored in the cache)
value = GFG(5)

# creates a Weak Value Dictionary
weak_dict = weakref.WeakValueDictionary()

# inserting value into the dictionary
weak_dict["num"] = value

# getting the weak ref count
print(f'Weak reference count is: {weakref.getweakrefcount(weak_dict)}') 

# deleting the weak dictionary
del weak_dict

# running this will generate error 
# print(weak_dict)
```

**输出:**

```py
Weak reference count is: 1
```

在上面的例子中，我们假设有一个非常大的对象被放在缓存中，所以我们创建了一个弱引用字典来存储这个键和值对，这样它将被垃圾收集。