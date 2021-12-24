# 如何在姜戈创建和使用信号？

> 原文:[https://www . geesforgeks . org/如何创建和使用 django 中的信号/](https://www.geeksforgeeks.org/how-to-create-and-use-signals-in-django/)

信号用于在修改模型实例时执行任何操作。信号是帮助我们将事件与行动联系起来的工具。我们可以开发一个函数，当一个信号调用它时，它就会运行。换句话说，信号用于在修改/创建数据库中的特定条目时执行一些操作。例如，一旦在数据库中创建新的用户实例，就需要创建一个配置文件实例

有 3 种信号。

1.  **pre_save/post_save** :此信号在方法 save()之前/之后工作。
2.  **pre_delete/post_delete** :这个信号在删除一个模型的实例(方法 delete())之前和之后工作，这个信号被抛出。
3.  **pre_init/post_init** :这个信号在实例化一个模型(_init__()方法之前/之后抛出。

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> 
> [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

### 如何使用 Django 的信号？

例如，如果我们想在使用 post_save 信号创建用户后立即创建用户的配置文件

**车型. py**

## 蟒蛇 3

```py
from django.db import models
from django.contrib.auth.models import User
from PIL import Image

class Profile(models.Model):
    user = models.OneToOneField(User, on_delete=models.CASCADE)
    image = models.ImageField(default='default.jpg', upload_to='profile_pics')

    def __str__(self):
        return f'{self.user.username} Profile'
```

**视图. py**

## 蟒蛇 3

```py
from django.shortcuts import render, redirect
from django.contrib import messages
from django.contrib.auth.decorators import login_required
from .forms import UserRegisterForm, UserUpdateForm, ProfileUpdateForm

def register(request):
    if request.method == 'POST':
        form = UserRegisterForm(request.POST)
        if form.is_valid():
            form.save()
            username = form.cleaned_data.get('username')
            messages.success(request, f'Your account has been created! You are now able to log in')
            return redirect('login')
    else:
        form = UserRegisterForm()
    return render(request, 'users/register.html', {'form': form})

@login_required
def profile(request):
    if request.method == 'POST':
        u_form = UserUpdateForm(request.POST, instance=request.user)
        p_form = ProfileUpdateForm(request.POST,
                                   request.FILES,
                                   instance=request.user.profile)
        if u_form.is_valid() and p_form.is_valid():
            u_form.save()
            p_form.save()
            messages.success(request, f'Your account has been updated!')
            return redirect('profile')

    else:
        u_form = UserUpdateForm(instance=request.user)
        p_form = ProfileUpdateForm(instance=request.user.profile)

    context = {
        'u_form': u_form,
        'p_form': p_form
    }

    return render(request, 'users/profile.html', context)
```

**Forms.py**

## 蟒蛇 3

```py
from django import forms
from django.contrib.auth.models import User
from django.contrib.auth.forms import UserCreationForm
from .models import Profile

class UserRegisterForm(UserCreationForm):
    email = forms.EmailField()

    class Meta:
        model = User
        fields = ['username', 'email', 'password1', 'password2']

class UserUpdateForm(forms.ModelForm):
    email = forms.EmailField()

    class Meta:
        model = User
        fields = ['username', 'email']

class ProfileUpdateForm(forms.ModelForm):
    class Meta:
        model = Profile
        fields = ['image']
```

**信号 py(使用接收器方法)**

## 蟒蛇 3

```py
# code
from django.db.models.signals import post_save, pre_delete
from django.contrib.auth.models import User
from django.dispatch import receiver
from .models import Profile

@receiver(post_save, sender=User)
def create_profile(sender, instance, created, **kwargs):
    if created:
        Profile.objects.create(user=instance)

@receiver(post_save, sender=User)
def save_profile(sender, instance, **kwargs):
        instance.profile.save()
```