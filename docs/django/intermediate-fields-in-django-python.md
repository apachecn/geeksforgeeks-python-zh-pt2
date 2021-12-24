# Django | Python 中的中间字段

> 原文:[https://www . geesforgeks . org/intermediate-field-in-django-python/](https://www.geeksforgeeks.org/intermediate-fields-in-django-python/)

**先决条件:** [姜戈模型](https://www.geeksforgeeks.org/django-models-set-1/)、[姜戈](https://www.geeksforgeeks.org/python-relational-fields-in-django-models/)中的关系字段

在 Django 中，当 A 的一个实例与 B 的多个实例相关时，两个模型 A 和 B 之间存在多对多的关系，反之亦然。例如–在商店管理系统中，一个项目和一个客户共享多对多关系，因为一个客户可以购买多个项目，多个客户可以购买同一个项目。

然而，可能有些字段既不是特定于客户的，也不是特定于购买的项目的，而是特定于客户购买的项目的。例如购买数量、购买日期等。为了存储这样的中间数据，我们需要中间模型。我们需要通过`ManyToManyField`中的`through`参数指定中间模型。

对于我们的例子，代码看起来像这样。

```py
from django.db import models

class Item(models.Model):
    name = models.CharField(max_length = 128)
    price = models.DecimalField(max_digits = 5, decimal_places = 2)

    def __str__(self):
        return self.name

class Customer(models.Model):
    name = models.CharField(max_length = 128)
    age = models.IntegerField()
    items_purchased = models.ManyToManyField(Item, through = 'Purchase')

    def __str__(self):
        return self.name

class Purchase(models.Model):
    item = models.ForeignKey(Item, on_delete = models.CASCADE)
    customer = models.ForeignKey(Customer, on_delete = models.CASCADE)
    date_purchased = models.DateField()
    quantity_purchased = models.IntegerField()
```

现在让我们看看如何创建我们的采购模型的实例。

```py
i = Item.objects.create(name = "Water Bottle", price = 100)
c = Customer.objects.create(name = "Abhishek", age = 21)
p = Purchase(item = i, customer = c, 
             date_purchased = date(2019, 7, 7), 
             quantity_puchased = 3)

p.save()
```

```py
c.items_purchased.all()
```

```py
<QuerySet [<Item: Water Bottle>]>
```

```py
i.customer_set.all()
```

```py
<QuerySet [<Customer: Abhishek>]>
```