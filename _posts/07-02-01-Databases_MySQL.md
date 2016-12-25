---
isChild: true
title:   MySQL 扩展
anchor:  mysql_extension
---

## MySQL 扩展 {#mysql_extension_title}

The [mysql] extension for PHP is incredibly old and has superseded by two other extensions:

- [mysqli]
- [pdo]

PHP 中的 [mysql] 扩展已经不再进行新的开发了，并且已经[在 PHP 5.5.0 版本中正式被废弃][mysql_deprecated]，在 **[PHP 7.0 中已经被正式移除][mysql_removed]**.

To save digging into your `php.ini` settings to see which module you are using, one option is to search for `mysql_*`
in your editor of choice. If any functions such as `mysql_connect()` and `mysql_query()` show up, then `mysql` is
in use.

Even if you are not using PHP 7.0 yet, failing to consider this upgrade as soon as possible will lead to greater
hardship when the PHP 7.0 upgrade does come about. The best option is to replace mysql usage with [mysqli] or [PDO] in
your applications within your own development schedules so you won't be rushed later on.

**If you are upgrading from [mysql] to [mysqli], beware lazy upgrade guides that suggest you can simply find and replace `mysql_*` with `mysqli_*`. Not only is that a gross oversimplification, it misses out on the advantages that mysqli provides, such as parameter binding, which is also offered in [PDO][pdo].**

* [PHP: MySQL增强版扩展][mysql_api]
* [MySQL 开发者 PDO 使用教程][pdo4mysql_devs]

[mysql]: http://php.net/mysql
[mysql_deprecated]: http://php.net/migration55.deprecated
[mysql_removed]: http://php.net/manual/en/migration70.removed-exts-sapis.php
[mysqli]: http://php.net/mysqli
[pdo]: http://php.net/pdo
[mysql_api]: http://php.net/mysqlinfo.api.choosing
[pdo4mysql_devs]: http://wiki.hashphp.org/PDO_Tutorial_for_MySQL_Developers
