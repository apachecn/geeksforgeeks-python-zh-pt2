# Django ORM–插入、更新&删除数据

> 原文:[https://www . geesforgeks . org/django-ORM-插入-更新-删除-数据/](https://www.geeksforgeeks.org/django-orm-inserting-updating-deleting-data/)

**先决条件:** [姜戈车型](https://www.geeksforgeeks.org/django-models/)

Django 允许我们使用一个名为 ORM(对象关系映射器)的数据库抽象 API 与它的数据库模型交互，即添加、删除、修改和查询对象。本文讨论了我们可以使用 Django ORM 执行的所有有用的操作。

出于演示目的，我们将使用以下 Django 模型。

```
class Album(models.Model):
    title = models.CharField(max_length = 30)
    artist = models.CharField(max_length = 30)
    genre = models.CharField(max_length = 30)

    def __str__(self):
        return self.title

class Song(models.Model):
    name = models.CharField(max_length = 100)
    album = models.ForeignKey(Album, on_delete = models.CASCADE)

    def __str__(self):
        return self.name
```

我们可以通过在项目目录中运行以下命令来访问 Django ORM。

```
python manage.py shell
```

这将我们带到一个交互式 Python 控制台。假设我们的模型存在于 **`myProject/albums/models.py`** 中，我们可以使用以下命令导入我们的模型:

```
>>> from books.models import Song, Album
```

### 添加对象

要创建相册模型的对象并将其保存到数据库中，我们需要编写以下命令:

```
>>> a = Album(title = "Divide", artist = "Ed Sheeran", genre = "Pop")
>>> a.save()
```

要创建宋模型的对象并将其保存到数据库中，我们需要编写以下命令:

```
>>> s = Song(name = "Castle on the Hill", album = a)
>>> s.save()
```

### 检索对象

为了演示，让我们再添加 2 张专辑唱片。

```
>>> a = Album(title = "Abbey Road", artist = "The Beatles", genre = "Rock")
>>> a.save()
>>> a = Album(title = "Revolver", artist = "The Beatles", genre = "Rock")
>>> a.save()
```

为了检索模型的所有对象，我们编写以下命令:

```
>>> Album.objects.all()
<QuerySet [<Album: Divide>, <Album: Abbey Road>, <Album: Revolver>]>
```

输出是一个 QuerySet，或一组与查询匹配的对象。请注意，打印的名称是`__str__()`功能的输出。

我们也可以使用功能`filter()`、`exclude()`和`get()`过滤查询。`filter()`函数返回一个对象与给定查找参数匹配的查询集。

```
>>> Album.objects.filter(artist = "The Beatles")
<QuerySet [<Album: Abbey Road>, <Album: Revolver>]>
```

`exclude()`函数返回一个查询集，该查询集的对象与给定的查询参数不匹配。

```
>>> Album.objects.exclude(genre = "Rock")
<QuerySet [<Album: Divide>]>
```

`get()`函数返回与给定查找参数匹配的单个对象。当查询返回多个对象时，它会给出错误。

```
>>> Album.objects.get(pk = 3)
<QuerySet [<Album: Revolver>]>
```

### 修改现有对象

我们可以按如下方式修改现有对象:

```
>>> a = Album.objects.get(pk = 3)
>>> a.genre = "Pop"
>>> a.save()
```

### 删除对象

要删除单个对象，我们需要编写以下命令:

```
>>> a = Album.objects.get(pk = 2)
>>> a.delete()
>>> Album.objects.all()
<QuerySet [<Album: Divide>, <Album: Revolver>]>
```

要删除多个对象，我们可以使用`filter()`或`exclude()`功能，如下所示:

```
>>> Album.objects.filter(genre = "Pop").delete()
>>> Album.objects.all()
<QuerySet []>
```