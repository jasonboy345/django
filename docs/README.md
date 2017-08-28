## 点击切换主题


<div class="demo-theme-preview">
  <a data-theme="vue">vue默认</a>
  <a data-theme="dark">dark黑色</a>
  <a data-theme="pure">pure纯净</a>
</div>


<style>
  .demo-theme-preview a {
    padding-right: 10px;
  }

  .demo-theme-preview a:hover {
    text-decoration: underline;
    cursor: pointer;
  }
</style>

<script>
  var preview = Docsify.dom.find('.demo-theme-preview');
  var themes = Docsify.dom.findAll('[rel="stylesheet"]');

  preview.onclick = function (e) {
    var title = e.target.getAttribute('data-theme')

    themes.forEach(function (theme) {
      theme.disabled = theme.title !== title
    });
  };
</script>


## Django

> 一个基于python的web框架

## 本文档内容
* 博客部署的曲折bug
* django入门 代码 图示说明 练习
* git使用
* django搭建博客
* 周老师讲解django知识点总结

## django手册
> [英文版](https://docs.djangoproject.com/en/1.11/)

> [中文版](http://python.usyiyi.cn/translate/Django111_LTS/index.html)

## 赞助

![微信支付](_media/wechat.png)




