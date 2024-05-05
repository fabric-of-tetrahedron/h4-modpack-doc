Fast backs 快速备份是一个支持增量备份的 Fabric 模组。
#### 支持功能

- 仅增量备份更改的文件；
- 比压缩更快、更小的备份文件；
- 本地备份；
- 远程备份到任何 git 服务器；
- 远程备份到任何服务器（不需要 git 服务器）；
- 自动计划备份；
- 简单恢复备份；
- 备份删减；
- LuckPerms 支持；
- 可工作在客户端和专用服务器；
- 可工作在 Linux，Windows 和 Mac 系统；
- 易用的命令；
- 以及更多。
#### 命令

- `/backup init` - 初始化，这个命令将会检查git和git-lfs是否安装等
- `/backup local` - 进行备份
- `/backup help` - 获取帮助
- `/backup enable`和`/backup disable` - 启用或关闭世界关闭时自动备份
- `/backup list` - 列出备份的快照
- `/backup restore` - 回档
  - 例如 `/backup restore 2022-10-02_10-11-12`
- `/backup delete` - 删除快照

兼容性：
- 

网址：
- https://www.mcmod.cn/class/9029.html
- https://modrinth.com/mod/fastback

下载地址：
- https://modrinth.com/mod/fastback/versions?l=fabric&g=1.20.1

所属整合包：
- [[百姓日用整合包]]