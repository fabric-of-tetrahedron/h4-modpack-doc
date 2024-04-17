这是一个运行在 Fabric 端的登录模组，提供了玩家账号功能，使离线模式的服务器变得更安全。

玩家命令

- `/login <password>, /l <password> - 登陆账号`
- `/logout - 退出登陆`
- `/register <password> <password> - 注册账号`
- `/account - 管理账号`
- `/unregister <password> - 注销账号`
- `/changePassword <old password> <new password> - 更改密码`

注释： 允许玩家用以下字符组合作为密码：纯字母, 字母与下划线_, "引号与字母" 或者 "字母与&$@#"。

管理员命令

- `/auth - 管理员命令`
- `/auth reload - 重新配置文件`
- `/auth setGlobalPassword <password> - 为服务器设置一个全局密码`
- `/auth setSpawn [<dimension id> <x> <y> <z>] - 设置一个出生点，在玩家登录过程中将他们临时传送至此`

- `/auth remove <uuid> - 将用户数据从数据库中删除`
- `/auth update <uuid> <password> -上传用户密码`
- `/auth register <uuid> <password> - 注册一个新用户`
- `/auth uuid <player> - 以小写形式输入玩家昵称将给出该昵称的离线 uuid`
- `/auth addToForcedOffline <player> - 将玩家添加至强制离线列表`
- `/auth list - 列出所有已注册玩家`

Note: right now show only that players who are a login since last start.

高级自动登录

作用：允许拥有 Mojang 账户的玩家绕过身份验证，如果玩家由 Mojang API 创建，他们将被视为在线玩家。

启用方法：
- 在 server.properties 中将 online-mode 更改为 true，然后在 EasyAuth 的配置文件中将 premiumAutologin 设置为 true。
- 启用后将创建一个“混合”在线服务器，购买了 Minecraft 的玩家可以跳过登陆过程并且拥有在线 uuid。
- 未购买 Minecraft 的玩家在加入服务器时必须注册/登陆，并且使用离线 uuid。
- 注意：只有原本为离线服务器并且玩家已拥有基于 uuid 的数据（例如村民折扣）时，你才应该启用此选项。
- 成就进度，玩家数据等将自动迁移，但如果一位在线玩家更改了用户名，他将失去所有数据，除非你手动迁移它们。
- 强制离线列表：通过将在线玩家加入强制离线列表可以让他们与离线玩家一样需要强制登陆并使用离线 uuid。
- 如果你想将一位玩家加入“强制离线列表”，请用小写字母将他的昵称添加至配置文件中的 forcedOfflinePlayers 列表里。
- 离线玩家无法登录：有些离线玩家可能与一名在线玩家拥有同样的昵称，你可以使用命令将他们添加至强制离线列表。

兼容性：
- 

网址：
- https://www.mcmod.cn/class/6241.html
- https://modrinth.com/mod/easyauth

下载地址：
- https://modrinth.com/mod/easyauth/versions?l=fabric&g=1.20.1

所属整合包：
- [[百姓日用整合包]]