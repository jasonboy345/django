# 动态URL
运行已经做好的博客框架, 会发现一个问题, 只有一个主页的空盒子, 而大部分时候我们希望能够让每篇博客文章都有一个独立的页面.

我第一个想到的方法是给每篇博客文章加一个view函数逻辑, 然后设置一个独立的url但是这种方法耦合性太强, 而且用户不友好, 缺点非常多

> Django给我们提供了一个方便的解决方法, 就是动态`URL`

现在修改my_blog/article/views.py代码:

![05-django-blog-view](_images/django-blog/05-django-blog-view.png)

因为id是每个博文的唯一标识, 所以这里使用id对数据库中的博文进行查找

在my_blog/my_blog/urls.py中修改url设置:

![05-django-blog-urs](_images/django-blog/05-django-blog-urs.png)

然后在templates下建立一个用于显示单页博文的界面:

```
#post.html
{% extends "base.html" %}

{% block content %}
<div class="posts">
        <section class="post">
            <header class="post-header">
                <h2 class="post-title">{{ post.title }}</h2>

                    <p class="post-meta">
                        Time:  <a class="post-author" href="#">{{ post.date_time|date:"Y /m /d"}}</a> <a class="post-category post-category-js" href="#">{{ post.category }}</a>
                    </p>
            </header>

                <div class="post-description">
                    <p>
                        {{ post.content }}
                    </p>
                </div>
        </section>
</div><!-- /.blog-post -->
{% endblock %}
```

可以发现只需要对home.html进行简单的修改, 去掉循环就可以了.

修改home.html和base.html, 加入动态链接和主页, 归档, 专题和About Me按钮
```
<!--home.html-->
{% extends "base.html" %}

{% block content %}
<div class="posts">
    {% for post in post_list %}
        <section class="post">
            <header class="post-header">
                <h2 class="post-title"><a href="{% url "detail" id=post.id %}">{{ post.title }}</a></h2>

                    <p class="post-meta">
                        Time:  <a class="post-author" href="#">{{ post.date_time |date:"Y /m /d"}}</a> <a class="post-category post-category-js" href="#">{{ post.category }}</a>
                    </p>
            </header>

                <div class="post-description">
                    <p>
                        {{ post.content }}
                    </p>
                </div>
                <a class="pure-button" href="{% url "detail" id=post.id %}">Read More >>> </a>
        </section>
    {% endfor %}
</div><!-- /.blog-post -->
{% endblock %}
```

```
<!--base.html-->
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="A layout example that shows off a blog page with a list of posts.">

    <title>Andrew Liu Blog</title>
    <link rel="stylesheet" href="http://yui.yahooapis.com/pure/0.5.0/pure-min.css">
    <link rel="stylesheet" href="http://yui.yahooapis.com/pure/0.5.0/grids-responsive-min.css">
    <link rel="stylesheet" href="http://picturebag.qiniudn.com/blog.css">

</head>
<body>
<div id="layout" class="pure-g">
    <div class="sidebar pure-u-1 pure-u-md-1-4">
        <div class="header">
            <h1 class="brand-title"><a href="{% url "home" %}">Andrew Liu Blog</a></h1>
            <h2 class="brand-tagline">雪忆 - Snow Memory</h2>
            <nav class="nav">
                <ul class="nav-list">
                    <li class="nav-item">
                        <a class="button-success pure-button" href="/">主页</a>
                    </li>
                    <li class="nav-item">
                        <a class="button-success pure-button" href="/">归档</a>
                    </li>
                    <li class="nav-item">
                        <a class="pure-button" href="#">Github</a>
                    </li>
                    <li class="nav-item">
                        <a class="button-error pure-button" href="#">Weibo</a>
                    </li>
                    <li class="nav-item">
                        <a class="button-success pure-button" href="/">专题</a>
                    </li>
                    <li class="nav-item">
                        <a class="button-success pure-button" href="/">About Me</a>
                    </li>
                </ul>
            </nav>
        </div>
    </div>

    <div class="content pure-u-1 pure-u-md-3-4">
        <div>
            {% block content %}
            {% endblock %}
            <div class="footer">
                <div class="pure-menu pure-menu-horizontal pure-menu-open">
                    <ul>
                        <li><a href="http://andrewliu.tk/about/">About Me</a></li>
                        <li><a href="http://twitter.com/yuilibrary/">Twitter</a></li>
                        <li><a href="#">GitHub</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</div>

</body>
</html>
```
其中主要改动

* 添加了几个导航按钮, 方便以后添加功能(暂时不添加登陆功能)
* 添加read more按钮
* 在博客文章的增加一个链接, 链接的href属性为{% url "detail" id=post.id %}, *当点击这个文章题目时, 会将对应的数据库对象的id传入的url中, 类似于url传参, 不记得的同学可以重新回到前几页翻一下. 这里将数据库对象唯一的id传送给url设置, url取出这个id给对应的view中的函数逻辑当做参数. 这样这个id就传入对应的参数中被使用

> 比如: 点击到的博客文章标题的对象对应的id=2, 这个id被传送到name=detail的url中, '^(?P<id>\d+)/$'正则表达式匹配后取出id, 然后将id传送到article.views.detail作为函数参数, 然后通过get方法获取对应的数据库对象, 然后对对应的模板进行渲染, 发送到浏览器中..

此时重新运行服务器, 然后在浏览器中输入http://127.0.0.1:8000/点击对应的博客文章题目, 可以成功的跳转到一个独立的页面中


![05-django-blog-url2.png](_images/django-blog/05-django-blog-url2.png)