# 使用 pickle 和 cPickle 模块序列化数据

> 原文:[https://www . geeksforgeeks . org/serialization-data-use-the-pickle-and-cpickle-modules/](https://www.geeksforgeeks.org/serializing-data-using-the-pickle-and-cpickle-modules/)

序列化是一个将对象存储为字节流或字符流的过程，以便通过网络传输它，或者将它存储在磁盘上，以便在需要时重新创建它及其状态。相反的过程称为反序列化。

在 python 中，Pickle 模块为我们提供了序列化和反序列化 Python 对象的方法。Pickle 是一个强大的库，它可以序列化许多其他库无法序列化的复杂和自定义对象。就像 Pickle 一样，有一个 cPickle 模块和 pickle 共享相同的方法，但是它是用 C 编写的，cPickle 模块是作为 C 函数而不是类格式编写的。

### 泡菜和鸡肉的区别:

*   Pickle 使用基于 python 类的实现，而 cPickle 是作为 C 函数编写的。因此，cPickle 比 Pickle 快很多倍。
*   Pickle 在 python 2.x 和 python 3.x 中都可用，而默认情况下 cPickle 在 python 2.x 中可用。要在 python 3.x 中使用 cPickle，我们可以导入 _pickle。
*   cPickle 不支持 Pickle 中的子类。如果子类化不重要，cPickle 更好，否则 Pickle 是最好的选择。

因为 pickle 和 cPickle 共享同一个接口，所以我们可以用同样的方式使用它们。以下是作为参考的示例代码:

## 蟒蛇 3

```py
try:

    # In python 2.x it is available as default
    import cPickle as pickle
except ImportError:

    # In python 3.x cPickle is not available
    import pickle

import random

# A custom class to demonstrate pickling 
class ModelTrainer:
    def __init__(self) -> None:
        self.weights = [0,0,0]

    def train(self):
        for i in range(len(self.weights)):
            self.weights[i] = random.random()

    def get_weights(self):
        return self.weights

# Create an object 
model = ModelTrainer()

# Populate the data
model.train()

print('Weights before pickling', model.get_weights())

# Open a file to write bytes
p_file = open('model.pkl', 'wb')

# Pickle the object
pickle.dump(model, p_file)
p_file.close()

# Deserialization of the file
file = open('model.pkl','rb')
new_model = pickle.load(file)

print('Weights after pickling', new_model.get_weights())
```

**输出:**

> 酸洗前的重量[0.6089721131909885，0.78999999995
> 
> 酸洗后的重量[0.6089721131909885，0.78999999995

在上面的代码中，我们已经创建了一个自定义类 ModelTrainer，它初始化了一个 0 的列表。train()方法用一些随机值填充列表，get_weight()方法返回生成的值。接下来，我们已经创建了模型对象并打印了生成的权重。我们已经在“写字节”模式中创建了一个新文件。dump()方法将对象作为字节流转储到文件中。验证是通过将文件加载到新对象中并打印权重来完成的。

Pickle 模块对于 python 对象非常强大。但是它只能保存数据，不能保存类结构。因此，如果我们不提供类定义，任何自定义类对象都不会加载。以下是描绘失败的示例:

## 蟒蛇 3

```py
try:
    # In python 2.x it is available as default
    import cPickle as pickle
except ImportError:

    # In python 3.x cPickle is not available
    import pickle

# Deserialization of the file
file = open('model.pkl','rb')
new_model = pickle.load(file)

print('Weights of model', new_model.get_weights())
```

**输出:**

> 追溯(最近一次通话持续时间):
> 
> 文件“des.py”，第 12 行，在
> 
> new_model = pickle.load(文件)
> 
> 属性错误:无法在<module from="">上获取属性“模型训练器”</module>

产生上述错误是因为我们当前的脚本不知道这个对象的类。因此，我们可以说 pickle 只保留了对象内部的数据，但是它不能保存方法和类结构。

为了纠正上述错误，我们必须向脚本提供类定义。以下是如何正确加载自定义对象的示例:

## 蟒蛇 3

```py
try:

    # In python 2.x it is available as default
    import cPickle as pickle
except ImportError:

    # In python 3.x cPickle is not available
    import pickle

import random

# If the file is available,
# we can use import statement to import the class

# A custom class to demonstrate pickling
class ModelTrainer:
    def __init__(self) -> None:
        self.weights = [0, 0, 0]

    def train(self):
        for i in range(len(self.weights)):
            self.weights[i] = random.random()

    def get_weights(self):
        return self.weights

# Deserialization of the file
file = open('model.pkl', 'rb')
new_model = pickle.load(file)

print('Weights of model', new_model.get_weights())
```

**输出:**

> 模型的权重[0.6089721131909885，0.78919431265203，0.7899994]

我们为模型训练器课程提供了参考。脚本现在可以识别该类，并且可以再次调用构造函数来构建对象。我们不需要键入整个类代码，只需从前面的文件中导入即可。

#### 序列化为字符串

我们还可以将对象序列化为字符串。Pickle 和 cPickle 模块提供转储()和加载()方法。dumps()方法将对象作为参数，并返回编码的字符串。load()方法则相反。它接受编码的字符串并返回原始对象。下面是将自定义对象序列化为字符串的代码。

## 蟒蛇 3

```py
try:

    # In python 2.x it is available as default
    import cPickle as pickle
except ImportError:

    # In python 3.x cPickle is not available
    import pickle

import random

# A custom class to demonstrate pickling 
class ModelTrainer:
    def __init__(self) -> None:
        self.weights = [0,0,0]

    def train(self):
        for i in range(len(self.weights)):
            self.weights[i] = random.random()

    def get_weights(self):
        return self.weights

# Create an object 
model = ModelTrainer()

# Populate the data
model.train()

print('Weights before pickling', model.get_weights())

# Pickle the object
byte_string = pickle.dumps(model)

print("The bytes of object are:",byte_string)

# Deserialization of the object using same byte string
new_model = pickle.loads(byte_string)

print('Weights after depickling', new_model.get_weights())
```

**输出:**

> 酸洗前的重量[0.92347412606742，0.9234983，0.9234999991
> 
> 对象的字节为:b ' \ X80 \ x03c _ _ main _ _ \ nModelTrainer \ NQ \ x00)\ x81q \ x01 } q \ x02X \ x07 \ x00 \ x00 \ x00 weightsq \ x03]q \ x04(G？\固定\x8d\x19\x9c\x8fL\xc3G？\xd6W\x97\x1e\x8aHHG？\xd8\x129\x01\xcb\xee\xf2esb。
> 
> 去毛后的重量[0.923474126606742，0.92493983，0.9226606767