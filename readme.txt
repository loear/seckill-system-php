1 开发环境：
nginx + mysql + redis + php

2 数据库文件
/data/miaosha.sql

3 配置文件
/conf/_local.inc.php

4 PHP版本
5.6

5 PHP组件
msql, pdo, redis, mcrypt

brew install php56-redis --build-from-source
brew install php56-mcrypt --build-from-source
brew upgrade php56-igbinary


6 站点根目录
/web/

7 数据库管理工具
/web/phpmyadmin/
http://127.0.0.1/phpmadmin/

8 系统管理后台
/web/admin/
http://127.0.0.1/admin/
用户名和密码都是 miaosha