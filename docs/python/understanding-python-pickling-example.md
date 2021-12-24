# 用例子理解 Python 酸洗

> 原文:[https://www . geesforgeks . org/understanding-python-酸洗-示例/](https://www.geeksforgeeks.org/understanding-python-pickling-example/)

先决条件:[酸洗模块](https://www.geeksforgeeks.org/pickle-python-object-serialization/)

Python pickle 模块用于序列化和反序列化 Python 对象结构。Python 中的任何对象都可以被腌制，以便保存在磁盘上。pickle 所做的是在将对象写入文件之前先“序列化”对象。酸洗是一种转换 python 对象(列表、字典等)的方法。)转换成字符流。想法是这个字符流包含在另一个 python 脚本中重建对象所需的所有信息。

```
# Python3 program to illustrate store 
# efficiently using pickle module 
# Module translates an in-memory Python object 
# into a serialized byte stream—a string of 
# bytes that can be written to any file-like object.

import pickle

def storeData():
    # initializing data to be stored in db
    Omkar = {'key' : 'Omkar', 'name' : 'Omkar Pathak',
    'age' : 21, 'pay' : 40000}
    Jagdish = {'key' : 'Jagdish', 'name' : 'Jagdish Pathak',
    'age' : 50, 'pay' : 50000}

    # database
    db = {}
    db['Omkar'] = Omkar
    db['Jagdish'] = Jagdish

    # Its important to use binary mode
    dbfile = open('examplePickle', 'ab')

    # source, destination
    pickle.dump(db, dbfile)                     
    dbfile.close()

def loadData():
    # for reading also binary mode is important
    dbfile = open('examplePickle', 'rb')     
    db = pickle.load(dbfile)
    for keys in db:
        print(keys, '=>', db[keys])
    dbfile.close()

if __name__ == '__main__':
    storeData()
    loadData()
```

**输出:**

```
omkarpathak-Inspiron-3542:~/Documents/Python-Programs{content}#xA0;python P60_PickleModule.py
Omkar => {'age': 21,  'name': 'Omkar Pathak',  'key': 'Omkar',  'pay': 40000}
Jagdish => {'age': 50,  'name': 'Jagdish Pathak',  'key': 'Jagdish',  'pay': 50000}

```

**腌制无档**

```
# initializing data to be stored in db
Omkar = {'key' : 'Omkar', 'name' : 'Omkar Pathak', 
'age' : 21, 'pay' : 40000}
Jagdish = {'key' : 'Jagdish', 'name' : 'Jagdish Pathak',
'age' : 50, 'pay' : 50000}

# database
db = {}
db['Omkar'] = Omkar
db['Jagdish'] = Jagdish

# For storing
b = pickle.dumps(db)       # type(b) gives <class 'bytes'>

# For loading
myEntry = pickle.loads(b)
print(myEntry)
```

**使用 Pickle Module 的优势:**

1.  **Recursive objects (including objects that refer to themselves):** Pickle will track the objects that it has serialized, so the references to the same objects will not be serialized in the future. (The marshaling module is interrupted because of this. )
2.  **Object sharing (reference to the same object in different places):** This is similar to self-referencing objects; Pickle stores the object only once and ensures that all other references point to the master copy. Shared objects remain shared, which is very important for mutable objects.
3.  **User-defined classes and their instances:** Marshal doesn't support these at all, but pickle can transparently save and restore class instances. Class definitions must be importable and stored in the same module as objects.

本文由 **Omkar Pathak** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。