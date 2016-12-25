---
isChild: true
anchor:  configuration_files
---

## 配置文件 {#configuration_files_title}

当你在为你的应用程序创建配置文件时，最好的选择时参照以下的做法：

- 推荐你将你的配置信息存储在无法被直接读取和上传的位置上。
- 如果你一定要存储配置文件在根目录下，那么请使用 `.php` 的扩展名来进行命名。这将可以确保即使脚本被直接访问到，它也不会被以明文的形式输出出来。
- Information in configuration files should be protected accordingly, either through encryption or group/user file
system permissions.
- It is a good idea to ensure that you do not commit configuration files containing sensitive information e.g. passwords or API tokens to source control.
