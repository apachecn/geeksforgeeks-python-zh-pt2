# 内置于姜戈

的&定制模型管理器

> 原文:[https://www . geesforgeks . org/内置-定制-模型-django 中的经理/](https://www.geeksforgeeks.org/built-in-custom-model-managers-in-django/)

Django manager 是一个类，它充当 Django 模型与数据库交互的接口。每个模型至少有一个管理器对象。它有很多方法和属性来简化数据库的工作。事实上，许多初级 Django 开发人员不知道他们使用 Manager 类对象来提取或创建所需的模型对象。Django 在模型中提供的默认 Manager 对象是“**对象**”。

**语法:**

要使用 Django 默认管理器对象，您必须遵循以下语法–

```py
model_name.objects.method
```

这里的“对象”是默认情况下姜戈创建的管理器对象。

**一个基本例子:**

假设我们有一个名为**医院**的模型类–

```py
class Hospital(models.Model):
    name = models.CharField(max_length=50)
    city = models.CharField(max_length=30)
    def __str__(self):
        return self.name
```

但是它还没有在数据库中创建任何对象。它只创建一个具有医院对象结构的空表。为了在数据库中创建这些对象，我们需要使用默认的 Django 管理器对象(因为我们不需要构建任何自定义管理器)-

```py
Hospital.objects.create(name='AIIMS',city ='Delhi')
```

“create”方法创建一个新对象。它接受模型类想要的字段值。在上面的代码行中，我们通过调用“create”方法创建了一个医院对象，该方法将字段值作为参数。

**给**默认管理器**起一个自定义名称:**

有时需要给默认管理器一个自定义名称。为此，您必须定义类型模型的类属性或字段。经理()。这里有一个例子

```py
class Student(models.Model):
    ...
    students = models.Manager() //now the default manager is named as students
```

此后，学生数据库表上的所有操作都必须使用“学生”管理器来完成–

```py
Student.students.filter(...) // here students manager is used
```

任何使用“对象”作为这个类的管理者的努力都会导致一个错误。

**经理类的方法:**

Manager 对象有许多内置方法来简化数据库操作。这里描述了一些最流行的方法–

<figure class="table">

| 全部() | 返回包含到目前为止创建的所有对象的查询集 |
| 过滤器(* *石英) | 返回包含与给定参数匹配的对象列表的查询集。如果没有找到匹配的对象，它将返回一个空的查询集。 |
| 排除(* *夸脱) | 它的作用与 filter()方法完全相反，即返回一个包含与给定参数不匹配的对象的 queryset。 |
| get（**kwargs） | 返回与给定参数匹配的单个对象。如果找到多个对象，它将抛出一个模型。MultipleObjectsReturned 返回错误。如果 get()没有找到任何对象，它将引发一个模型。不存在异常。 |
| 创建(**kwargs) | 用给定的参数创建一个新对象。 |
| order _ by(*字段) | 根据传入的参数设置先前返回的 queryset 的顺序。 |

</figure>

**示例:**

以下示例使用 python 命令外壳。

```py
>>> h1 = Hospital.objects.create(name="Calcutta Medical",city="kolkata")
>>> h2 = Hospital.objects.create(name="dummy",city="Chennai")     #creating objects using create() and save all these new objects into database
>>> h3 = Hospital.objects.create(name="TATA cancer Hospital",city="Mumbai")
>>> h4 = Hospital.objects.create(name="AIIMS Delhi",city="Delhi")
>>> h5 = Hospital.objects.create(name='NRS hospital",city="kolkata")
...
>>> Hospital.objects.filter(city='kolkata')  # returns queryset of objects whose city attribute is 'kolkata'
<QuerySet [<Hospital: Calcutta Medical>, <Hospital: NRS hospital>]>
>>> Hospital.objects.get(city='Delhi')
<Hospital: AIIMS Delhi>
>>> Hospital.objects.get(city='kolkata') # raise error as there are multiple objects
```

这些是最流行的方法。然而，这种方法的数量是巨大的。您可以查看 django 文档以获得完整的参考。

**创建自定义经理:**

有时，您可能希望 django manager 以某种方式工作，而默认的 manager 不这样做。在这种情况下，你可以自己定制经理。程序很简单。您必须创建一个继承自管理器类的类。这里有一个例子

**示例:**

我们来谈谈医院模式。我们正在创建一个名为 custom manager 的自定义管理器，它类似于默认的 django 管理器，除了一点。当我们调用 CustomManager 对象的 all()方法时，我们不会得到所有的对象。取而代之的是，我们将得到所有那些城市=加尔各答的物体

## 蟒蛇 3

```py
class CustomManager(models.Manager):
  '''first we get all objects from the database by
  calling the get_queryset method of the inherited class
  i.e. Manager class using super().get_queryset().
  After that we are filtering objects having city attribute equal to kolkata
  and return the filtered objects'''
  get_queryset(self):
    return super().get_queryset().filter(city= 'kolkata')
```

每个管理器类都有一个 get_queryset 方法。它用于根据作为参数的属性获取对象的 queryset。如果没有提供参数，那么它将返回所有对象。在这个例子中，我们通过继承 manager 类并只重写 get_queryset 方法来创建一个自定义 django 管理器。

所以我们定义了一个自定义管理器。现在我们要做的就是把这个经理和医院模型联系起来–

## 蟒蛇 3

```py
class Hospital(models.Model):
  name = models.CharField(max_length=50)
  city = models.CharField(max_length=30)
  objects = models.Manager() # our default django manager
  kolkata_hospitals = CustomManager() # creating our custom manager object
  def __str__(self):
    return self.name
```

医院模型有两个管理者对象。现在如果我们调用医院对象，我们得到所有的医院对象。但是当我们调用医院.加尔各答 _ 医院. all()时，我们只会得到那些城市是加尔各答的对象。

请注意，如果在同一个模型中使用多个管理器对象，则需要注意管理器对象的定义顺序。第一个定义的管理器对象将被视为默认管理器对象。例如–在上面的示例中，“对象”是默认管理器，因为它是首先定义的。Django 在一些内部流程中使用默认管理器。因此，在选择默认经理时要小心，否则你可能会得到一些意想不到的结果。如果您想将一个管理器设为默认，并且该管理器对象没有首先定义，那么您可以通过将元类的 default_manager_name 设置为等于该对象名称来将其定义为默认管理器。

```py
class Hospital(models.Models):
    ...
    class Meta:
        default_manager_name = 'kolkata_hospitals' # default manager is now kolkata_hospitals not objects
```

您可以使用自定义管理器做任何您想做的事情。你可以定义一个新的方法来修改数据库中的一些数据，或者返回一些东西。不是每个 manager 方法都必须返回一个 queryset。事实上，您可以定义不返回任何内容的方法。

如果您想了解更多信息，请查看 Django 在经理–[https://docs.djangoproject.com/en/3.0/topics/db/managers/](https://docs.djangoproject.com/en/3.0/topics/db/managers/)上的官方文档