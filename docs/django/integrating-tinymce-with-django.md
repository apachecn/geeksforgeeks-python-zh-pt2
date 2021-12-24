# 将 TinyMCE 与 Django 整合

> 原文:[https://www . geeksforgeeks . org/integrating-tinymce-with-django/](https://www.geeksforgeeks.org/integrating-tinymce-with-django/)

TinyMCE 是一个在线富文本编辑器，完全灵活，并提供定制。主要用于获取动态数据，如 GFG 的文章等等，它们不是静态的帖子数据库

**安装–**

要将其与 Django 网络应用程序或网站集成，您需要首先安装其 pip 库

```
pip install django-tinymce

```

**与姜戈项目整合–**

在 setting.py 中添加 tinyMCE 作为单个应用程序

```
INSTALLED_APPS = [
     ...
    'tinymce',
     ... 
]

```

还可以在 settings.py 中添加 tinyMCE 编辑器的默认配置

```
TINYMCE_DEFAULT_CONFIG = {
    'cleanup_on_startup': True,
    'custom_undo_redo_levels': 20,
    'selector': 'textarea',
    'theme': 'silver',
    'plugins': '''
            textcolor save link image media preview codesample contextmenu
            table code lists fullscreen  insertdatetime  nonbreaking
            contextmenu directionality searchreplace wordcount visualblocks
            visualchars code fullscreen autolink lists  charmap print  hr
            anchor pagebreak
            ''',
    'toolbar1': '''
            fullscreen preview bold italic underline | fontselect,
            fontsizeselect  | forecolor backcolor | alignleft alignright |
            aligncenter alignjustify | indent outdent | bullist numlist table |
            | link image media | codesample |
            ''',
    'toolbar2': '''
            visualblocks visualchars |
            charmap hr pagebreak nonbreaking anchor |  code |
            ''',
    'contextmenu': 'formats | link image',
    'menubar': True,
    'statusbar': True,
}

```

在 configuration dictionary 中，您可以通过更改主题等值来自定义编辑器。

现在完成了 TinyMCE 的设置，将它带入到我们需要的操作中。使用一些必需的值，比如输入字段的大小，在 html 页面上显示内容时会用到它

```
from django import forms
from tinymce import TinyMCE
from .models import _your_model_

class TinyMCEWidget(TinyMCE):
    def use_required_attribute(self, *args):
        return False

class PostForm(forms.ModelForm):
    content = forms.CharField(
        widget=TinyMCEWidget(
            attrs={'required': False, 'cols': 30, 'rows': 10}
        )
    )
    class Meta:
        model = _your_model_
        fields = '__all__'
```

最后一步是将 html 字段添加到您的模型中，您也可以使用不同的字段在他们的官方网站上查看它们

```
...
from tinymce.models import HTMLField 

class article(models.Model):
    ...
    content =  HTMLField()
```

所有这些都设置好了，只需通过运行以下命令在管理页面中进行迁移以查看更改

```
python manage.py makemigrations

```

```
python manage.py migrate
```

现在通过运行服务器在管理区域检查它

```
python manage.py runserver

```

**输出–**

这里它看起来会有不同的外观

![html field](img/ca7cc827c798d9892ff2024a7a8fd1bc.png)

管理区的编辑