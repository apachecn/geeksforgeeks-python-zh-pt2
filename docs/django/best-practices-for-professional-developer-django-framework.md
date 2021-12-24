# 专业开发人员的最佳实践–姜戈框架

> 原文:[https://www . geeksforgeeks . org/best-practices-for-professional-developer-django-framework/](https://www.geeksforgeeks.org/best-practices-for-professional-developer-django-framework/)

Django 是一个基于 Python 的开源框架，用于构建网络应用程序。为了使我们的 Django 代码更加易读和高效，我们应该遵循一定的规则/实践。这些不应该被视为与 Django 合作的正确方式或唯一方式，而是与 Django 框架合作的最佳实践

## <u>编码风格</u>

一般来说，代码应该干净、简洁、可读、可测试和干燥(不要重复自己)。尽量遵循 [PEP8](https://www.python.org/dev/peps/pep-0008/) 的指导方针尽可能合理。

## <u>使用虚拟环境</u>

避免对项目依赖使用全局环境，因为它会产生依赖冲突。Python 不能同时使用多个包版本。如果不同的项目需要同一个包的不同的不兼容版本，这可能是一个问题。始终在虚拟环境中隔离您的项目需求和依赖关系。最常见的方法是使用 [virtualenv。](https://docs.python.org/3/tutorial/venv.html)

## <u>需求. txt 文件</u>

需求是项目运行时使用的 Python 包(依赖项)列表，包括每个包的版本。更新您的 requirements.txt 文件对于与其他开发人员正确协作非常重要。当这个文件包含在您的代码库中时，您可以通过在终端中执行一行代码来更新虚拟环境中安装的所有包。

要生成新的 requirements.txt 文件或更新现有文件，请使用此命令。确保您在正确的目录中。

```py
(virtualenv) $ pip freeze > requirements.txt

```

在将代码推送到存储库之前，update requirements.txt 文件，从存储库拉取代码之后，安装 requirements . txt 文件是一个很好的做法。

## <u>避免写胖视图</u>

你应该写胖模型，瘦视图，这意味着试着把你的大部分逻辑写在模型本身。

例如:假设我们正在实现一个向用户发送电子邮件的功能，不如用电子邮件功能扩展模型，而不是在你的控制器/视图中写入这个逻辑。这使得您的代码更容易进行单元测试，因为您可以在一个地方测试电子邮件逻辑，而不是在发生这种情况的每个控制器/视图中重复测试。

## <u>正确的车型命名</u>

一般来说，模型代表一个单一的对象或实体，因此模型名称应该是一个单数名词。

```py
# Bad practice
class Users(models.Model):
  pass

# Good practice
class User(models.Model): # use 'User' instead of 'Users'
  pass
```

## <u>在模型关系中使用正确的相关名称</u>

相关名称指定从父模型到子模型的反向关系。当它返回一个 queryset 时，用复数表示相关名称是合理的

```py
# parent model
class Owner(models.Model):
    pass

# child model
class Item(models.Model):
    # use "items" instead of "item"
    owner = models.ForeignKey(Owner, related_name ='items')
```

## <u>姜戈模板</u>

**位置** : 模板可以放在两个地方，或者是 app 目录本身，或者是项目的根目录。建议将模板放在根目录中，但是如果您想让您的应用程序可重复使用(在多个位置使用)，那么您应该将其放在应用程序目录中。

```py
#Good practice
root_folder/
    my_app1/
    my_app2/
    my_app3/
    templates/

#If you want to make your app reusable
root_folder/
    my_app1/
        templates/
    my_app2/
        templates/
    my_app3/
        templates/

```

**命名**:正确命名你的模板有助于任何一个新开发人员立即获得你的 django 代码。好的模板名称是这样的

```py
[application]/[model]_[function].html

```

例如，创建一个模板来列出我的地址簿(地址簿应用程序)中的所有联系人(联系人模型)，我将使用以下模板:

```py
address_book/contact_list.html

```

类似地，联系人的详细视图将使用

```py
address_book/contact_detail.html

```