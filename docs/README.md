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

## 是什么



## 特性
- 无需构建，写完文档直接发布


## 例子



