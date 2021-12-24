# 在姜戈运行额外脚本

> 原文:[https://www . geesforgeks . org/running-extra-scripts-in-django/](https://www.geeksforgeeks.org/running-extra-scripts-in-django/)

当你有一些新的想法可以用于网络开发和 Python 时，总是需要运行额外的脚本或进程！！！一直都是。

它可以是任何可能包括数据加载、数据处理和数据清理的脚本，也可以是在视图或模型中直接提供业务逻辑的应用程序并不总是最好的时候的任何 ML 阶段。由于 django 约定指的是“瘦视图”，我们必须尝试删除逻辑，并尝试将其嵌入到其他一些文件中。

Django 扩展在一个包中，使您能够运行额外的脚本，您需要使用 pip 安装它，使用终端和类型

```
pip install django-extensions        
```

在 setting.py 文件中找到的已安装应用程序中添加 django-extensions

```
INSTALLED_APPS = [
    ...
    ...
    'django_extensions',
]
```

现在在你的项目中创建一个名为 scripts 的文件夹，其中包含所有你可以执行的 python 文件
添加一个名为‘_ _ init _ _’的空 python 文件。py '这指定脚本也是 Django 项目的一部分

创建包含您需要执行的代码的新文件，命名您喜欢的任何内容

示例:在运行服务器之前将数据从 CSV 文件加载到数据库

*T1T3】*

```
import csv
from site.models import Destination

def run():
    # All data in run method only will be executed 
    fhand = open('location.csv')
    reader = csv.reader(fhand)
    next(reader)

    for row in reader:
        latitude = row[0]
        longitude = row[1]
        name = row[2]
        item = Destination.objects.create(name=name,latitude=latitude,longitude=longitude)
        item.save()

    print("Data Added")
```

现在要运行脚本，只需如下所示激发命令，其中“load”是文件名

```
python manage.py runscript load
```