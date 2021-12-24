# 姜戈应用模型–Python manage . py make migrations 命令

> 原文:[https://www . geesforgeks . org/django-app-model-python-manage-py-make migrations-command/](https://www.geeksforgeeks.org/django-app-model-python-manage-py-makemigrations-command/)

根据文档，迁移是 Django 传播您对模型所做更改的方式(添加字段、删除模型等)。)到您的数据库模式中。它们主要是自动设计的，但是您需要知道何时进行迁移、何时运行迁移以及可能遇到的常见问题。

***进行迁移*** 是通过以下命令运行的

```
Python manage.py makemigrations
```

如果上面的命令说没有检测到任何变化，您也可以对单个应用程序进行更改。
例如，如果你有 10 个名为 a、b、c、d、e、f、g、h、I、j 的应用程序，你可以为这些应用程序单独运行 makemigrations。

```
Python manage.py makemigrations a 
```

```
Python manage.py makemigrations b 
```

```
Python manage.py makemigrations c 
```

等等。

## Django 应用模型制作迁移

***进行迁移*** 基本上为预安装的应用程序(可以在 settings.py 中的已安装应用程序中查看)和您在已安装应用程序中添加的新创建的应用程序模型生成 SQL 命令。它不会执行数据库文件中的那些命令。所以在 makemigrations 之后不会创建表。

在应用 make migration 之后，您可以看到那些带有 SQL grid 的 SQL 命令，它显示了 make migration 生成的所有 SQL 命令。

例如，如果我们制作一个模型类-

```
from django.db import models

class Person(models.Model):
    first_name = models.CharField(max_length = 30)
    last_name = models.CharField(max_length = 30)
```

使用 makemigrations 后，相应的 sql 命令将是

```
CREATE TABLE myapp_person (
"id" serial NOT NULL PRIMARY KEY,
"first_name" varchar(30) NOT NULL,
"last_name" varchar(30) NOT NULL
);

```

使用上面的命令，当我们使用 migrate 时，将在数据库中创建表。