# yii2-tech
# 后台管理系统beta

## 安装说明：

```bash
git clone https://github.com/anruence/yii2-tech.git
cd yii-tech
composer install
```

## 数据库迁移
 - tech.sql中保存了sql语句，暂时没写migrate脚本。后续会扩展。

修改测试环境的common/config/main-local.php文件

> environments/dev/common/config/main-local.php

正式环境对应
> environments/prod/common/config/main-local.php

```php
<?php
return [
    'components' => [
        'db' => [
            'class' => 'yii\db\Connection',
            'dsn' => 'mysql:host=localhost;dbname=tech',
            'username' => 'your-username',
            'password' => 'your-password',
            'charset' => 'utf8',
        ],
        //...
    ],
];

```


```bash
php yii migrate

php yii migrate --migrationPath=@yii/rbac/migrations

## 使用了yii2-admin组件，如果需要配置菜单执行下面命令

php yii migrate --migrationPath=@mdm/admin/migrations

```

提供了sql文件，可以用命令直接导入。

```bash
mysql -uusername -ppassword dbname < tech.sql
```
## 效果图

[![前端页面](http://oss-cn-qingdao.aliyuncs.com/hljstatic/default/20161215/7c12ce2166205222.png "前端页面")](anruence.com "前端页面")

[![后台管理](http://oss-cn-qingdao.aliyuncs.com/hljstatic/default/20161215/32eecb68c2205114.png
 "后台管理")](mis.dev.anruence.com "后台管理")

## nginx配置

TBD
```

```