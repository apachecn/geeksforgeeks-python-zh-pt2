# 在姜戈模型

中添加废料场

> 原文:[https://www . geesforgeks . org/add-the-slug-field-inside-django-model/](https://www.geeksforgeeks.org/add-the-slug-field-inside-django-model/)

### **姜戈的斯拉格菲尔德是什么？**

这是一种生成有效网址的方法，通常使用已经获得的数据。例如，使用文章的标题来生成网址。让我们假设我们的博客有一个标题为“极客的姜戈书”的帖子，主键 id= 2。我们可以参考这篇文章

```py
www.geeksforgeeks.org/posts/2\. 
```

或者，我们可以参考标题

```py
 www.geeksforgeeks.org/posts/The Django book by Geeksforgeeks. 
```

但问题是 URL 中的空格是无效的，需要用 *%20* 替换，很难看，变成了下面这样

```py
www.geeksforgeeks.org/posts/The%20Django%20book%20by%20geeksforgeeks 
```

但这不是解决有意义的网址。另一个选择是

```py
 www.geeksforgeeks.org/posts/the-django-book-by-geeksforgeeks
```

所以，这种鼻涕虫现在是“django-by-geeks forgeeks”。所有字母都是小写的，空格用连字符-。

假设我们的博客文章模型看起来与此相似。

## 蟒蛇 3

```py
STATUS_CHOICES = (
   ('draft', 'Draft'),
   ('published', 'Published'),
)

class Post(models.Model):
   title = models.CharField(max_length = 250)
   slug = models.SlugField(max_length = 250, null = True, blank = True)
   text = models.TextField()
   published_at = models.DateTimeField(auto_now_add = True)
   updated = models.DateTimeField(auto_now = True)

   status = models.CharField(max_length = 10, choices = STATUS_CHOICES,
                                                      default ='draft')

   class Meta:
       ordering = ('-published_at', )

   def __str__(self):
       return self.title
```

### **将 Slugify** 添加到**我们的项目中:**

现在我们需要找到一种自动将标题转换成鼻涕虫的方法。我们希望这个脚本在每次创建 *Post* 模型的新实例时被触发。为此，我们将使用信号。

**注意:**在保存 settings.py 文件的同一目录下添加新文件 util.py。

## 蟒蛇 3

```py
import string, random
from django.db.models.signals import pre_save
from django.dispatch import receiver
from django.utils.text import slugify

def random_string_generator(size = 10, chars = string.ascii_lowercase + string.digits):
    return ''.join(random.choice(chars) for _ in range(size))

def unique_slug_generator(instance, new_slug = None):
    if new_slug is not None:
        slug = new_slug
    else:
        slug = slugify(instance.title)
    Klass = instance.__class__
    max_length = Klass._meta.get_field('slug').max_length
    slug = slug[:max_length]
    qs_exists = Klass.objects.filter(slug = slug).exists()

    if qs_exists:
        new_slug = "{slug}-{randstr}".format(
            slug = slug[:max_length-5], randstr = random_string_generator(size = 4))

        return unique_slug_generator(instance, new_slug = new_slug)
    return slug
```

### **姜戈的信号:**

在许多情况下，当模型实例中有修改时，我们需要执行一些操作。Django 为我们提供了一种处理这些情况的优雅方式。信号是允许将事件与动作相关联的实用程序。我们可以开发一个函数，当一个信号调用它时，它就会运行。
在定义了帖子模型的帖子 app 的 models.py 文件中，将此添加到同一文件中:

## 蟒蛇 3

```py
@receiver(pre_save, sender=Post)
def pre_save_receiver(sender, instance, *args, **kwargs):
   if not instance.slug:
       instance.slug = unique_slug_generator(instance)
```

*预保存接收器*功能应单独放置在 Post 模型之外。

**注意:**在 urls.py 中用路径(' posts'，detail)编辑详细路径。在视图中，用
编辑细节功能

## 蟒蛇 3

```py
def detail(request, slug):
    q = Post.objects.filter(slug__iexact = slug)
   if q.exists():
       q = q.first()
   else:
       return HttpResponse('<h1>Post Not Found</h1>')
   context = {

       'post': q
   }
   return render(request, 'posts/details.html', context)
```

最后一步是在 HTML 文件[中添加链接查看](”/posts/{{)。现在我们准备去*127 . 0 . 0 . 1:8000/帖子/标题-您已经添加了*，它将向您显示页面*details.html*。