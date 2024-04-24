现代化修复（ModernFix）

一款集各类功能于一身的性能优化模组，可以提高性能、降低内存占用并修复现代 MC 版本（1.16 +）中的许多问题，同时不会严重影响游戏体验。本模组大约能让大多数 Forge 1.16.5 -1.19.2 的整合包启动速度加快两倍。如果启用了一些默认未启用的选项，甚至能让 ATM 8 这样大型的整合包在 3 GB 以下的内存占用中运行。  

现代化修复是自由、开源的软件，所有源码可在 GitHub Repo 中获取。

![现代化修复 (ModernFix)-第1张图片](https://i.mcmod.cn/editor/upload/20231007/1696666601_257643_lzoY.webp)

目录:
- 1 现代化修复（ModernFix）
- 2 技术性摘要
- 3 遇到问题时该去哪
- 4 如何支持这个项目？
- 5 模组推荐
- 6 模组兼容
- 6.1 区块保存修复
- 6.2 Saturn
- 6.3 Modern UI
- 6.4 流畅加载
- 7 更多信息
- 8 相似 Mod 传送门

技术性摘要

现代化修复究竟对你的游戏做了什么？有很多调整——太多了，无法在此逐一总结。不过，下面简要介绍了优化的一般类型：  

- 从较新版本的 MC 和 / 或 Forge 中移植错误修正的代码，例如，本模组解决了在 1.18 中移除维度模组时世界会损坏的问题。
- 为不再支持特定 MC 版本的模组打补丁，以改善游戏体验，而不是要求玩家更新。
- 对游戏启动过程进行了多项优化和改进，大大提高了速度，减少了随机的并发性崩溃。
- 提供更多调试工具，帮助模组作者和玩家找到某些罕见的游戏崩溃/冻结原因，而不是依赖痛苦的二分法。
- 包含了完全重新设计过的 MC 模型加载系统，可即时、动态地加载模型，虽然这因兼容性问题在默认情况下并不启用。模型加载是自 1.8 以来 MC 模组主要的性能退步之一，而这个新系统减轻了各种各样的弊端，使内存占用和加载速度更加符合 1.7.10 版本。
- 想分配极少内存（如 512 MB 甚至更少）但流畅地玩原版？现在你可以做到了。请访问 Wiki 上的“超低内存占用”页面。

如果你精通技术并想了解每个补丁的更多细节，可以阅读 补丁概述 Wiki 页面。  

#### 遇到问题时该去哪

在评论区发出遇到的问题当然可以，但是模组作者 [embeddedt](https://www.mcmod.cn/author/25256.html "embeddedt") 并非国人，显然难以在此处回应。

因此，请在 GitHub 上报告问题，或加入 Discord 并在 #modernfix-discussion 频道中提问。现代化修复仍处于积极维护的状态，问题是可以解决的。

请务必说明你使用的 MC 版本、模组加载器和现代化修复版本，以及安装的其他模组。  

#### 如何支持这个项目？

你可以通过两种主要方式帮助支持现代化修复的开发：

帮助宣传！在整合包中测试现代化修复，并鼓励整合包作者将现代化修复包含在整合包内。  

若你足够慷慨，可以通过 Ko-fi 支持 embeddedt。捐赠不是必须的（现代化修复也是免费的），但每一点小钱都很有帮助。embeddedt 利用空余时间开发现代化修复，因此收到的任何捐赠都有助于维持开发工作。

#### 模组推荐

MC 有很多性能优化模组，这里无法逐一列举它们，但在 embeddedt 看来，这里有一些必不可少的：

- 在 1.19.4 之前，请始终安装 [DFU 载入优化](https://www.mcmod.cn/class/3407.html)，因为它可以消除 DFU 系统造成的巨大延迟。
- 在 1.20 之前的任何版本中，一般都应该使用 [星光](https://www.mcmod.cn/class/3303.html)，除非它跟你的其它模组有兼容性问题（这种情况很少见）。它能大大提高光照引擎的性能，还能解决在区块之间移动时的 FPS 卡顿问题。另外，1.16 下官方的星光不支持机械动力，请改用 [Starlight x Create](https://www.mcmod.cn/class/5335.html "Starlight x Create") 。
- 请始终安装 [铁氧体磁芯](https://www.mcmod.cn/class/3888.html)，因为 Mojang 对方块状态/模型的实现低效地令人发指，且一旦添加的内容超过原版提供的内容，内存就会被迅速消耗。
- 安装 [Shutup Experimental settings](https://www.mcmod.cn/class/3448.html "Shutup Experimental settings")（1.19 之前）或 [Yeetus Experimentus](https://www.mcmod.cn/class/11062.html "Yeetus Experimentus")（1.19 以上）之类的模组。这些模组会阻止游戏弹出实验性功能屏幕，否则会导致游戏重新加载两次资源。

另外，embeddedt 不建议在任何情况下使用 [高清修复](https://www.mcmod.cn/class/36.html)。它是闭源的，打的补丁很容易破坏 Forge 和其它模组，而且会大大减慢游戏启动速度，通常会慢上几分钟。请考虑改用 [Sodium](https://www.mcmod.cn/class/2785.html)（Fabric） 或 [Embeddium](https://www.mcmod.cn/class/12028.html)（Forge）。现代化修复将不会解决任何与高清修复潜在的相关兼容性问题。

#### 模组兼容

[区块保存修复](https://www.mcmod.cn/class/7247.html)

2023 年 6 月 2 号之前发布的版本包含了它的功能来源，但之后，embeddedt 发现区块保存问题并没有被这个模组修复，遂将此代码删除。

[Saturn](https://www.mcmod.cn/class/7722.html)

Saturn 通过修复了占用大量内存的生物群系温度缓存内存泄漏来提高性能，但是本模组已经（更暴力地）移除了生物群系的温度缓存。

所以，你可以把 Saturn 和本模组安装在一起，但作者认为 Saturn 将不会发挥任何作用来源。

但是在 4 月，Saturn 却重新从“修复”转向“移除”来源，但还包含极少量额外的内存分配优化。

[Modern UI](https://www.mcmod.cn/class/2454.html)

本模组对 JEI 的线程优化与 Modern UI 存在一些兼容性问题，因此在检测到 Modern UI 存在时不允许手动启用，因为作者认为这在 Tooltip 渲染上有一定概率会导致出错来源。

默认情况下，本模组的 JEI 线程优化功能是默认关闭的。1.16.5 曾经默认开启这个功能，但是 5.9.0 之后也改为了默认关闭。如果你想开启该功能，可以进入 config/modernfix-mixins.properties，加上一行 mixin.perf.async_jei=true，重启游戏即可见效。

如果你在安装了 Modern UI 时仍然想开启 JEI 线程优化，则额外需要为自己的启动器加上下面这一行 JVM 参数

-Dmodernfix.unsupported.allowOverriding=true

在此基础上，如果你和作者一样认为这是有风险的，可以进入 config/ModernUI/client.toml 关闭 Modern UI 的 Tooltip 样式。

作者表示，虽然此 Tooltip 问题的风险较低，但他还是更倾向于直接禁用 JEI 线程优化，而有经验的玩家总是会知道该调整哪些 config 的来源。

[流畅加载](https://www.mcmod.cn/class/3422.html)

在 1.13.0（这是 MC 1.16.5 下的现代化修复版本号，对应 1.18.2 的 2.4.0，1.19.2 的 3.4.0）版本之前，此模组间接地与本模组不兼容，因为它限制了后台工作的线程数量，这可能会减慢加载速度，而那之后，ModernFix 已经能够兼容流畅加载，同时使用两者不应当再导致启动变慢来源。

它为降低服务器线程优先级而进行的调整已被本模组所包含。

#### 更多信息

本模组使用了 Sodium 的配置系统，所有的 mixin 都可以通过配置文件修改。

你可以在 Wiki 里找到本模组的 mixin 配置信息。

本模组还允许你在 Minecraft 1.16.5 Forge 环境下使用 Java 17，使用更高版本的 Java 可以获得更好的性能，只需配合 Wiki 中的 JVM 参数启动游戏即可。

#### 相似 Mod 传送门

1.12.2：[Vintage Fix](https://www.mcmod.cn/class/10728.html "VintageFix")

1.7.10：[Archaic Fix](https://www.mcmod.cn/class/8687.html "Archaic Fix")

兼容性：
- 

网址：
- https://www.mcmod.cn/class/8714.html
- https://modrinth.com/mod/modernfix

下载地址：
- https://modrinth.com/mod/modernfix/versions?l=fabric&g=1.20.1

所属整合包：
- [[性能优化整合包]]