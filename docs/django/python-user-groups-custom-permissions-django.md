# Python | Django 中具有自定义权限的用户组

> 原文:[https://www . geesforgeks . org/python-用户-组-自定义-权限-django/](https://www.geeksforgeeks.org/python-user-groups-custom-permissions-django/)

让我们考虑一下旅行预订服务，他们如何处理不同的计划和套餐。该公司提供了一份订购不同套餐的用户可以购买的产品清单。一般来说，他们遵循的理念是不同产品的水平分布。

让我们看看旅游预订服务提供的不同套餐:

1.  **首发计划**:在此套餐中，订户将获得非交流公交出行的便利，并且只能在非交流房间停留 1 天。假设这次旅行是从德里到哈里发(北方邦的一个宗教场所)。
2.  **黄金计划**:会比入门计划贵一些。在该计划中，订户将在非空调房间停留 2 天，乘坐空调巴士旅行，行程将从德里到哈里德瓦、里什凯什和穆索里。
3.  **钻石计划**:这是最昂贵的计划，将为订户提供 3 天的交流巴士和交流客房住宿计划，以及哈里德沃、里什凯什和穆索里之旅和水上公园之旅。

我们的主要目标是以非常高效的方式(遵循 [DRY 原则](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself))为后端设计和编写代码。
在姜戈有多种实现方法，但最合适和有效的方法是将用户分组并定义这些组的权限。该特定组的用户将自动继承该特定组的权限。让我们首先定义用户模型:

创建 Django 应用程序**用户**。在 models.py 文件的“用户”app 目录下，编写以下代码。

## 蟒蛇 3

```py
# importing necessary django classes
from django.contrib.auth.models import AbstractUser
from django.utils import timezone
from django.db import models

# User class
class User(AbstractUser):

    # Define the extra fields
    # related to User here
    first_name = models.CharField(_('First Name of User'),
                            blank = True, max_length = 20)

    last_name = models.CharField(_('Last Name of User'),
                            blank = True, max_length = 20)

# More User fields according to need

    # define the custom permissions
    # related to User.
    class Meta:

        permissions = (
            ("can_go_in_non_ac_bus", "To provide non-AC Bus facility"),
            ("can_go_in_ac_bus", "To provide AC-Bus facility"),
            ("can_stay_ac-room", "To provide staying at AC room"),
            ("can_stay_ac-room", "To provide staying at Non-AC room"),
            ("can_go_dehradoon", "Trip to Dehradoon"),
            ("can_go_mussoorie", "Trip to Mussoorie"),
            ("can_go_haridwaar", "Trip to Haridwaar"),
            ("can_go_rishikesh", "Trip to Rishikesh"),

# Add other custom permissions according to need.
```

迁移完上面写的模型后，我们有两个选项来创建组。

1.  **姜戈管理面板**:在管理面板中你会看到**组**以粗体显示，点击它，组成 3 个不同的组，分别命名为 0 级、1 级、3 级。另外，根据需要定义自定义权限。
2.  **通过编程创建一个有权限的组**:使用 python manage.py shell 打开 python shell。

## 蟒蛇 3

```py
# importing group class from django
from django.contrib.auth.models import Group, Permission
from django.contrib.contenttypes.models import ContentType

# import User model
from users.models import User

new_group, created = Group.objects.get_or_create(name ='new_group')

# Code to add permission to group
ct = ContentType.objects.get_for_model(User)

# If I want to add 'Can go Haridwar' permission to level0 ?
permission = Permission.objects.create(codename ='can_go_haridwar',
                                        name ='Can go to Haridwar',
                                                content_type = ct)
new_group.permissions.add(permission)
```

我们将以同样的方式为所有三个组设置不同的权限集。在此之前，我们已经创建了组，并将其与自定义权限相链接。

现在，检查特定用户是否正在访问适当的功能，例如，设置限制*级别 0* 不能访问*级别 1 用户*或*级别 2 用户*的功能，以此类推。为此，请检查每个视图函数的权限。
这里要非常小心，对于基于函数的视图，我们将简单地使用自定义装饰器。

**例如:**

## 计算机编程语言

```py
@group_required('level0')
def my_view(request):
    ...
```

更多详情请参考[本](https://djangosnippets.org/snippets/10508/)。
当我们谈论基于类的视图时，事情变得有点复杂，我们不能简单地添加装饰器函数，而是必须创建一个权限混合类。

**例如:**

## 计算机编程语言

```py
class GroupRequiredMixin(object):
    ...............
    ....Class Definition.....

class DemoView(GroupRequiredMixin, View):
  group_required = [u'admin', u'manager']

  # View code...
```

更多详情请参考[本](https://gist.github.com/ceolson01/206139a093b3617155a6)。

**参考文献:**
1。[https://docs . djangproject . com/en/1.11/topics/基于类的视图/mixins/](https://docs.djangoproject.com/en/1.11/topics/class-based-views/mixins/)
2。[http://Brad Montgomery . blogspot . in/2009/04/limited-按组访问 in-django.html](http://bradmontgomery.blogspot.in/2009/04/restricting-access-by-group-in-django.html)
3。[https://simpleisbetterthancomplex . com/2015/12/07/work-with-django-view-decorators . html](https://simpleisbetterthancomplex.com/2015/12/07/working-with-django-view-decorators.html)
4。[https://micropyramid . com/blog/custom-decorator-to-check-user-roles-and-permissions-in-django/](https://micropyramid.com/blog/custom-decorators-to-check-user-roles-and-permissions-in-django/)