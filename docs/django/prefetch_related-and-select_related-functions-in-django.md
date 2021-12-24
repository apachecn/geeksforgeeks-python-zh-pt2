# django 中的预取相关和选择相关功能

> 原文:[https://www . geesforgeks . org/prefetch _ related-and-select _ related-functions-in-django/](https://www.geeksforgeeks.org/prefetch_related-and-select_related-functions-in-django/)

在 Django 中，select_related 和 prefetch_related 旨在阻止因访问相关对象而导致的数据库查询泛滥。在本文中，我们将看到它如何减少查询数量，并使程序运行得更快。

*   **Select _ related ()** "Follow" the foreign key relationship, and select additional related object data when executing the query.
*   **Prefetch _ related ()** Find each relationship individually and "connect" it in Python.

当您要选择的对象是单个对象时，可以使用 select_related，例如 OneToOneField 或 ForeignKey。当你要得到一组东西时，你可以使用 prefetch_related，如此多的 ToManyFields 就像你说的或者反向的 ForeignKeys。只是为了澄清我所说的“反向外键”是什么意思。

**举例说明 Prefetch_related 和 select_related 的概念–**

上面的分类可能不太清楚，我们来看一个例子:

```py
class A(models.Model):
   pass

class B(models.Model):
   a = ForeignKey(ModelA)

# Forward ForeignKey relationship
A.objects.select_related('a').all()

# Reverse ForeignKey relationship
A.objects.prefetch_related('modelb_set').all() 
```

select_related 通过多表连接关联查询一次获取所有数据，通过减少数据库查询次数来提高性能。它使用 SQL 的 JOIN 语句，通过减少 SQL 查询的数量来优化和提高性能。后者是通过 JOIN 语句解决 SQL 查询中的问题。但是对于多对多关系，用 SQL 语句来解决并不明智，因为 JOIN 得到的表会很长，会导致 SQL 语句运行时间和内存占用的增加。prefetch_related()的解决方案是分别查询每个表，然后用 Python 处理它们的关系！

这里有一些例子:

`Models.py reads as follows:`

```py
from django.db import models

class Province(models.Model):
   name = models.CharField(max_length = 10)
   def __unicode__(self):
       return self.name

class City(models.Model):
   name = models.CharField(max_length = 5)
   province = models.ForeignKey(Province)
   def __unicode__(self):
       return self.name

class Person(models.Model):
   firstname = models.CharField(max_length = 10)
   lastname = models.CharField(max_length = 10)
   visitation = models.ManyToManyField(City, related_name = "visitor")
   hometown = models.ForeignKey(City, related_name = "birth")
   living = models.ForeignKey(City, related_name = "citizen")
   def __unicode__(self):
       return self.firstname + self.lastname
```

**select_related–**

我们使用了 select _ related()函数:

```py
>>> citys = City.objects.select_related().all()
>>> for c in citys:
...   print c.province
...
```

只有一个 SQL 查询，这显然大大减少了 SQL 查询的数量:

```py
SELECT `Optimize_city`.`id`, `Optimize_city`.`name`,
`Optimize_city`.`province_id`, `Optimize_province`.`id`, `Optimize_province`.`name`
FROM`Optimize_city`
INNER JOIN `Optimize_province` ON
(`Optimize_city`.`province_id`=`Optimize_province`.`id`);
```

**prefetch _ related–**

这里我们可以看到 Django 使用了 INNER JOIN。我想澄清一件事，优化是我们应用的一个名字。如果要获取湖北所有的城市名称，可以这样做:

```py
> HB=Province.objects.prefetch_related('city_set').get(name__iexact=u"Hubei Province")
>>> for city in hb.city_set.all():
...   city.name
...
```

触发 SQL 查询:

```py
SELECT `Optimize_province`.`id`, `Optimize_province`.`name`
FROM `Optimize_province`
WHERE `Optimize_province', `name `LIKE'Hubei Province';

SELECT `Optimize_city`.`id`, `Optimize_city`.`name`, `Optimize_city`.`province_id`
FROM `Optimize_city`
WHERE `Optimize_city`.`province_id` IN (1);
```

可以看到，预取是使用 IN 语句实现的。这样，当 QuerySet 中有太多对象时，根据数据库的特性，可能会出现性能问题。