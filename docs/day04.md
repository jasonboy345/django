# 第四天

## 知识点

### 做网线
* 线序
* 交叉线
* 直连线

### 子网掩码

> 作用划分网段和主机地址

```
192.168.201.21/24

相当于
ip 					192.168.201.21
netmask 			255.255.255.0
192.168.201.0    	主播地址 又叫网段地址
192.168.201.255  	广播地址
1-254           	本网段可以容纳254台主机 




192.168.201.21/25

相当于
ip 					192.168.201.21
netmask 			255.255.255.128
192.168.201.0   	主播地址 又叫网段地址
192.168.201.127  	广播地址
1-126           	本网段可以容纳126台主机 

```

### ubuntu配置ip
* [ubuntu配置ip](http://www.cnblogs.com/linjiqin/archive/2013/06/21/3148346.html)

```
1、修改配置文件/etc/network/interfaces
root@ubuntu:~# sudo gedit /etc/network/interfaces

添加以下内容：
auto eth0                  #设置自动启动eth0接口
iface eth0 inet static     #配置静态IP
address 192.168.11.88      #IP地址
netmask 255.255.255.0      #子网掩码
gateway 192.168.11.1        #默认网关

2、修改DNS
sudo gedit /etc/resolve.conf

nameserver 127.0.0.1 #记得加上
nameserver 8.8.8.8 #当地dns服务器(用ipconfig /all 查看本地dns，第一个dns是默认的，共有2个dns)

注：#后面的注释信息不要加进去。

3、重启网络，使配置生效
sudo /etc/init.d/networking restart

4、查看ip是否配置成功 root@ubuntu:~# ifconfig
```



### python自动化脚本配置ip





## 任务

#### 爬虫+大数据
* 优酷三层 
* python 配置IP和netmask 自动化脚本

#### linux网络和安全
* python 配置IP和netmask 自动化脚本

#### web
* 慕课+极客学院 页面还原度100%