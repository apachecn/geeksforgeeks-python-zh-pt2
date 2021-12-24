# 模型中的元类–姜戈

> 原文:[https://www.geeksforgeeks.org/meta-class-in-models-django/](https://www.geeksforgeeks.org/meta-class-in-models-django/)

Django 是一个高级 Python Web 框架，它鼓励快速开发和干净、实用的设计。它由经验丰富的开发人员构建，解决了许多网络开发的麻烦，因此您可以专注于编写应用程序，而无需重新发明轮子。这是免费的开源软件。

> 点击此处查看更多关于姜戈车型的信息–[姜戈车型](https://www.geeksforgeeks.org/django-models/)
> 
> T5】

**什么是模型元？**

模型元基本上是模型类的内部类。

模型元基本上用于改变模型字段的行为，比如改变顺序选项、verbose_name 和许多其他选项。在模型中添加元类是完全可选的。

要使用模型元，你必须像这样在你的模型中添加类元

```py
class student(models.Model):
    class Meta:
        options........
```

**模型元选项**

模型元有很多选项，你可以在模型的内部类元中给你的模型

**1。摘要**

如果抽象=真，这个模型将是一个抽象基类

## python 3

```py
class student(models.Model):
  class Meta:
      abstract = True
```