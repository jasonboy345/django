# 第五天

## 知识点
> 三种web身份验证方式-作用反爬虫

### session
* 普通web多用这种认证用户
* http协议 字符串协议
* cookie session记录用户登录信息,会话跟踪
* PV(访问量)：即Page View, 即页面浏览量或点击量，用户每次刷新即被计算一次。
* UV(独立访客)：即Unique Visitor,访问您网站的一台电脑客户端为一个访客。00:00-24:00内相同的客户端只被计算一次。
* Request Headers `Cookie`  `User-Agent`
* Response Headers `Content-Type:`

### 接口 RESTful API
* 移动端多用这种认证用户,85%的APP使用这种
* OpenID+签名认证

### 基于令牌访问 Token
* Token授权机制,令牌回收
* 基于微博 微信 discuz二次开发

### 总结三种web认证方式
* 标准 cookie session
* 接口 
* 令牌

### 用于爬取的方式
* python python_request urlopen 
* linux工具 curl wget 
* 其他工具 前端测试工具 火车头采集器


## 任务

### 爬虫+大数据
* 爬取用户登录后的页面 `python_request urlopen curl wget 前端测试工具 火车头采集器`
* 优酷三层 
* python 配置IP和netmask 自动化脚本

### linux网络和安全
* 在线课程linux配置24例
* python 配置IP和netmask 自动化脚本

### web
* 慕课+极客学院 页面还原度100%

