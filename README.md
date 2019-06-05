# 适合中小企业销售客户，代理商管理的一套系统

## 网商云CRM介绍-主要功能
一个软件企业的高效的CRM管理系统，前后端分离Vue+PHP 可以优秀高效的运行在腾讯云上
1. 客户资源管理
2. 正式客户会员客户管理
3. 销售业绩提成管理
4. 代理商管理
5. 公司人事销售数据统计
6. 基本的公司人事管理
7. 支持各种插件的二次开发


### Demo体验
超管理员账号：root@admin.com 密码：123456  
普通用户账号：bb@qq.com 密码：123456  
可以使用上面账号登录PC端和小程序端
###### pc端地址：  
https://democrm.netbcloud.com

###### 小程序端：  
![小程序体验二维码](https://images.gitee.com/uploads/images/2019/0307/131830_8af2ceeb_4805633.jpeg "tapd_30621563_1551325672_69.jpg")
### 使用教程
https://gitee.com/netbcloud/crm/wikis/pages
### 下载地址
https://gitee.com/netbcloud/crm/attach_files

### 软件架构
软件架构说明VUE PHP MYSQL 支持腾讯云分布式 CDN COS 读写分离

### 软件环境
PHP7及以后
MYSQL 5.6
nginx：1.12
### 安装教程

1. 系统的入口在public/index.php，nginx配置在该目录下
2. 第一次安装系统要用工具导入根目录的vue.sql（最新的）才能使用系统
3. 根目录下的.env文件，修改当前的数据库配置信息
4. 配置伪静态，接口才能访问

### 使用说明

#### 首次使用系统
pc端：
1.	安装好PHP环境，新建站点，配置好ssl证书。
2.	在站点配置文件里面配置伪静态：伪静态代码如下：配置nginx的静态
```
location / {
		try_files $uri $uri/ /index.php?$query_string;
	}
```
3. 系统的入口在public/index.php，设置运行目录为public
4.	新建数据库将根目录下的vue.sql文件导入到数据库。
5.	重命名根目录下的.env.example文件为.env，填写你当前的数据库信息、修改缓存、邮箱配置
6.	根目录public里的static、index.html、wgo.ico是vue前端文件，public/uploads是图片资源目录
7.	系统的售后提成金额自动加到销售人员的余额，需要配置服务器的定时任务，定时访问url地址：域名+/admin/updateAfterSale，如www.xxx.com/admin/updateAfterSale
8.	后台测试账号：root@admin.com 123456

小程序端：
1.	发布小程序，必须要先安装pc端，小程序与pc端，共用一个后台
2.	注册小程序账号，拿到appid跟secret等信息，配置好小程序域名
3.  拷贝wxapp目录到本地，使用微信开发者工具，新建项目
4.	修改utils里的server.js，配置上对应的域名地址
5.	登录pc端，依次打开，系统配置=》站点配置=》微信，在微信appid和微信secret里面填上小程序的appid和secret
6.	使用微信开发者工具上传代码，进入微信公众平台提交审核发布代码即可


源码目录结构：
```
根目录
|--public              站点运行目录
|     |----static      VUE前端文件
|     |----index.html  VUE前端文件
|     |----wgo.ico     VUE前端文件
|     |----uploads     图片资源文件
|--.env                环境配置文件
|--sourcecode     
|     |--wxapp         小程序前端文件
|     |--view          vue前端源码  
```

#### 后期版本

1. 按照CHANGELOG.md中记录的时间（需大于系统安装时间）从小到大在命令行中更新，完成后才可以使用代码。

#### 参与贡献

1. 总策划兼项目经理：车贯(Michael)
2. 研发团队：陈元  许堉颖   陈镇松  李迪
3. 设计产品：龙芳 林鸿耿
4. 特别支持：刘远航 袁程远


#### 其他支持

1. 微购儿小程序 [www.wegouer.com](http://www.wegouer.com) 正在使用
2. 网渠道科技 后浪云计算 百花盛放科技 浩瀚云科技 正在使用
3. 本套CRM是一套完整的客户管理系统，建立在微信/企业微信上使用
4. [ntbcloud](http://www.netbcloud.com/crm) 网商云官网CRM最新信息
