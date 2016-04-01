title: Vtiger
date: 2016-03-4 22:34:44
tags: crm
---

#Vtiger
##介绍

    vtiger6.0演示地址：http://vtiger6.vtcrm.cn/
    用户名：admin
    密 码：admin

##源码下载和安装
* [https://www.vtiger.com/open-source-downloads/](https://www.vtiger.com/open-source-downloads/)
* [http://community.vtiger.com/help/vtigercrm/administrators/installation.html](http://community.vtiger.com/help/vtigercrm/administrators/installation.html)

将解压的文件全部复制到/var/www/或根据/etc/apache2/sites-available配置的目录.

##安装依赖
apache mysql php php-imap php-curl php-xml

apt-get install php5-imap
apt-get install php5-curl

php5enmod imap
service apache2 restart

/etc/php5/apache2/php.ini 修改apache2的php设置

##相关链接
* [vtiger中文网|vtigercrm技术|vtiger本土化](http://www.vtcrm.cn/)
* [How to Install LAMP in Ubuntu 14.04 LTS](http://engineerbabu.com/2014/09/13/how-to-install-lamp-in-ubuntu/)
* [How to install VtigerCRM in ubuntu 14.04](http://engineerbabu.com/2014/10/03/install-vtigercrm-ubuntu-14-04/)
* [中文语言包](https://marketplace.vtiger.com/extensions?id=18)

##错误

#[How can enable imap in php.ini](http://stackoverflow.com/questions/23242402/how-can-enable-imap-in-php-ini)

    sudo apt-get install php5-imap
    sudo php5enmod imap
    sudo service apache2 restart

#Invalid command 'Header'

    /var/www/.htaccess: Invalid command 'Header'

需要开启模块

    sudo a2enmod headers


#[PHP不能创建目录](http://stackoverflow.com/questions/20563662/mkdir-permission-denied-in-var-www-vtiger-includes-runtime-viewer-php)

    mkdir(): Permission denied in /var/www/vtiger/includes/runtime/Viewer.php

需要修改文件夹拥有者

    cd /var/www
    chown -R www-data:www-data .

#Problem can't login {"success":false,"error":{"code":"Illegal request","message":"Illegal request"}}

通过本机地址登陆,密码正确的情况下出现Illegal request

    vi config.inc.php
    $site_URL = 'http://127.0.0.1/';
