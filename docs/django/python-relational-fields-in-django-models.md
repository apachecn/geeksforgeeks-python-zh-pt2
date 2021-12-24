# Django 模型中的 Python |关系字段

> 原文:[https://www . geesforgeks . org/python-relative-field-in-django-models/](https://www.geeksforgeeks.org/python-relational-fields-in-django-models/)

Prerequisite: [Django models](https://www.geeksforgeeks.org/django-models-set-1/)

Django 模型代表真实世界的实体，真实世界的实体完全相互独立的情况很少。因此，Django 支持关系数据库，并允许我们在不同的模型之间建立关系。Django 支持三种类型的关系字段:多对一、多对多和一对一。

## 多对一字段:

当一个模型 A 的一条记录与另一个模型 b 的多条记录相关时使用，例如–一个模型**歌曲**与一个模型**专辑**具有多对一的关系，即一张专辑可以有多首歌曲，但一首歌曲不能是多张专辑的一部分。使用 **`django.db.models`** 的 **`ForeignKey`** 字段定义多对一关系。

下面是一个例子来证明这一点。

```py
from django.db import models

class Album(models.Model):
    title = models.CharField(max_length = 100)
    artist = models.CharField(max_length = 100)

class Song(models.Model):
    title = models.CharField(max_length = 100)
    album = models.ForeignKey(Album, on_delete = models.CASCADE)
```

将多对一字段命名为与相关模型同名的小写字母是一种很好的做法。

## 多对多字段:

当一个模型 A 的一条记录与另一个模型 B 的多条记录相关联时使用，反之亦然。比如——一个模型**书**和一个模型**作者**有多对多的关系，即一本书可以由多个作者写，一个作者可以写多本书。使用 **`django.db.models`** 的 **`ManyToManyField`** 字段定义多对多关系。

下面是一个例子来证明这一点。

```py
from django.db import models

class Author(models.Model):
    name = models.CharField(max_length = 100)
    desc = models.TextField(max_length = 300)

class Book(models.Model):
    title = models.CharField(max_length = 100)
    desc = models.TextField(max_length = 300)
    authors = models.ManyToManyField(Author)
```

用相关模型的复数形式(小写)来命名多对多字段是一种很好的做法。这两个模型中的哪一个包含多对多字段并不重要，但不应该放在两个模型中。

## 一对一字段:

当模型 A 的一条记录正好与另一个模型 b 的一条记录相关时，使用该字段。如果对象以某种方式扩展了另一个对象，则该字段可以用作该对象的主键。比如——一辆**车**和一辆**车**是一对一的关系，即车就是车。使用 **`django.db.models`** 的 **`OneToOneField`** 字段定义一对一关系。

下面是一个例子来证明这一点。

```py
from django.db import models

class Vehicle(models.Model):
    reg_no = models.IntegerField()
    owner = models.CharField(max_length = 100)

class Car(models.Model):
    vehicle = models.OneToOneField(Vehicle, 
          on_delete = models.CASCADE, primary_key = True)
    car_model = models.CharField(max_length = 100)
```

最好将一对一字段命名为与相关模型同名的小写字母。

## 数据完整性选项:

因为我们正在创建依赖于其他模型的模型，所以当一个模型中的相应记录被删除时，我们需要定义另一个模型中的记录的行为。这是通过在关系字段中添加可选的 **`on_delete`** 参数来实现的，该参数可以取以下值:

*   **`on_delete = models.CASCADE`**–这是默认值。删除记录时，它会自动删除所有相关记录。(例如，删除专辑记录时，与之相关的所有歌曲记录都将被删除)
*   **`on_delete = models.PROTECT`**–阻止删除与其他记录有关系的记录。(例如，任何删除相册记录的尝试都将被阻止)
*   **`on_delete = models.SET_NULL`**–如果设置了 **`null = True`** ，则删除记录时，会将空值赋给关系字段。
*   **`on_delete = models.SET_DEFAULT`**–当记录被删除时，它为关系字段分配默认值，必须提供默认值。
*   **`on_delete = models.SET()`**–可以取默认值作为参数，也可以是可调用的，返回值将赋给字段。
*   **`on_delete = models.DO_NOTHING`**–不采取行动。使用这个值是不好的做法。