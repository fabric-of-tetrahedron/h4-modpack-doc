这个模组移除了在 Java 版 1.19 及更高版本中附加在每条聊天信息上的加密签名。移除这些签名后，微软就无法追踪你的聊天信息，也无法将聊天信息与 Minecraft 以及微软账户联系起来。

**在 1.19.1 后，这个模组也将禁用聊天举报功能。**

**注意：只有当服务器禁用聊天举报时，本模组才会完全有效。如果您讨厌开启聊天举报的服务器，作者建议不要在上面游玩。**

相同功能的 [Spigot 插件](https://modrinth.com/plugin/freedomchat)（非必要）。

#### 安装与使用

##### 仅限客户端

当这个模组被安装在客户端时，客户端将拒绝向服务器发送账户的公钥，并将签名从你发送的信息中剥离。因此，试图举报你发送的信息就没有用了，因为没有证据证明它们是由你的账户发送的。服务器将转发这些信息，**除非在服务器选项中把 enforce-secure-profile 设置为 true。** 这种情况下你无法加入服务器。

##### 仅限服务端

当这个模组被安装在服务端时，客户端在向服务器发送消息时仍然会附上签名，但服务器在将消息转发给其他玩家之前会将其剥离。因此，聊天举报功能对服务器中的玩家是无效的。在聊天设置中启用了 “仅显示安全的聊天”选项的玩家将无法阅读其他玩家的信息。你也可以手动配置 Mod，将玩家信息转换为系统信息，以规避该选项。不过这可能会导致其他修改玩家聊天的其它 Mods 无法使用。

##### 客户端+服务端

当这个模组同时被安装在客户端和服务端时，在向服务器发送消息之前，客户端的签名将被剥离，服务器不会尝试验证消息的签名。聊天举报功能和“仅显示安全的聊天”不会生效。当玩家试图使用这些功能时，会被通知这些功能已被该模组禁用。

该模组在只存在于服务端时可以正常使用，不过用户也可以将它被配置为需要客户端也强制安装，以便有完整的功能。你也可以只在服务端安装该模组。配置文件名为 NoChatReports.json，位于默认配置文件夹中。

##### 致开发者

‎如果您正在开发自己的模组、插件或其他服务器软件，欲阻止聊天报告，则可以使用客户端的 No Chat Reports 将您的软件服务器识别为安全。我详情请阅读此‎‎文章‎‎。如需要说明与更多帮助，请通过 Discord 与作者联系。‎

顺带一提，如果安装在客户端，这个模组将禁用遥测功能（类似于 [No Telemetry](https://www.mcmod.cn/class/6705.html "No Telemetry") 的做法）。  

为了使 Velocity 与这个模组兼容，你需要在 velocity.toml 中把 force-key-authentication 设置为 false。

图片![NCR禁用聊天举报 (No Chat Reports)-第1张图片](https://i.mcmod.cn/editor/upload/20230116/1673873366_343440_Bbth.webp)

![NCR禁用聊天举报 (No Chat Reports)-第2张图片](https://i.mcmod.cn/editor/upload/20230105/1672893890_343440_YhvG.webp)

![NCR禁用聊天举报 (No Chat Reports)-第3张图片](https://i.mcmod.cn/editor/upload/20230105/1672893890_343440_pFPr.webp)

![NCR禁用聊天举报 (No Chat Reports)-第4张图片](https://i.mcmod.cn/editor/upload/20230105/1672893891_343440_gUxV.webp)

兼容性：
- 

网址：
- https://www.mcmod.cn/class/6756.html
- https://modrinth.com/mod/no-chat-reports

下载地址：
- https://modrinth.com/mod/no-chat-reports/versions?l=fabric&g=1.20.1

所属整合包：
- [[百姓日用整合包]]