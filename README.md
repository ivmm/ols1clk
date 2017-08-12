# ols1clk - OpenLiteSpeed 一键包
========

介绍
--------

ols1clk 是 OpenLiteSpeed 的一键安装包。使用 ols1clk 可以快速安装 OpenLiteSpeed 以及 PHP、MariaDB 等环境组件，并且还提供了方便 WordPress 安装的相关参数。

**支持安装的系统：**

* Oracle 7 


特性
--------

1. 事件驱动架构，节省 CPU 和内存凯旋
2. WEB GUI 后台界面并提供实时统计
3. 不限制并发数，低负载压力
4. 支持 **LS Cache** 高性能页面缓存
5. 兼容 Apache mod_rewrite 语法
6. PHP-LiteSpeed 比 php-fpm、mod_php 更高效
7. 支持 HTTPS、HTTP/2、TLS1.2 1.3

安装
--------

**在 SSH 终端中运行：**

```bash
wget https://raw.githubusercontent.com/ivmm/ols1clk/oel/ols1clk.sh
chmod 755 ols1clk.sh

./ols1clk.sh [选项1] [选项2] …*
```

如果不添加 `选项` 设置，会以默认参数运行

###示例

**自动安装 OpenLiteSpeed + MariaDB10.2 + PHP5.6**

```bash
./ols1clk.sh
```

**自动安装 OpenLiteSpeed + MariaDB10.2 + PHP5.6 并安装 WP**

```bash
./ols1clk.sh -w
```

**自动安装 OpenLiteSpeed + MariaDB10.1 + PHP7.0 并安装 WP**

```bash
./ols1clk.sh --lsphp 70 --mariadbver 10.1
```

**自动安装 OpenLiteSpeed + MariaDB10.2 + PHP7.1，并安装 WP 指定域名为 www.mf8.biz**

```bash
./ols1clk.sh -a pa55w0rd -e your@email.com --lsphp 71 -w --wordpressplus www.mf8.biz
```


####选项

* **--adminpassword(-a) [PASSWORD]:** 设置 LiteSpeed 控制面板的密码，如果不设置就随机生成并在终端中显示。 例如：`-a pa55w0rd`
* **--email(-e) EMAIL:** 	设置管理员电子邮件。 例如：`-e your@email.com`
* **--lsphp VERSION:** 安装以 php-litespeed 方式运行的 PHP，目前支持：54、55、56、70、71
* **--mariadbver VERSION:** 安装 MariaDB 官方提供的二进制 MariaDB Server，目前支持：10.0 10.1 10.2
* **--wordpress(-w):** 自动安装 WordPress
* **--wordpressplus SITEDOMAIN:** 设置运行 WP 网站的域名
* **--wordpresspath WORDPRESSPATH:** 设置 WP 所安装的路径
* **--dbrootpassword(-r) [PASSWORD]:** 设置 MySQl 的 root 账户密码，若不填写则自动生成并在终端中显示
* **--dbname DATABASENAME:** 设置 WP 所安装的数据名
* **--dbuser DBUSERNAME:** 设置 WP 所安装的数据用户
* **--dbpassword [PASSWORD]:** 设置 WP 所安装的数据密码
* **--listenport WORDPRESSPORT:** 服务所运行的端口, 默认80
* **--wpuser WORDPRESSUSER:** 设置 WP 管理员用户名
* **--wppassword [PASSWORD]:** 设置 WP 管理员米啊么
* **--wplang WORDPRESSLANGUAGE:** 设置 WP 语言，zh_CN 表示中文，默认英文
* **--sitetitle WORDPRESSSITETITLE:** 设置 WP 网站标题, 默认为 mySite.
* **--uninstall:** 卸载 OpenLiteSpeed 并移除相关文件
* **--purgeall:** 卸载 OpenLiteSpeed、MariaDB 并移除相关文件
* **--version(-v):** 显示版本悉尼下
* **--help(-h):** 查看帮助


