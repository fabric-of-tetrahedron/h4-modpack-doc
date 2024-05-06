这篇文章同时适用于[[如何将Mod从forge移植到fabric]]

参考
- https://www.reddit.com/r/feedthebeast/comments/102jpqk/comment/j2xom9w/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button
- 

1. 创建新项目，保持相同的ModID和包名等
2. 修复gradle fabric 的mod依赖项
3. 将所有assets文件粘贴到新项目
4. 根据能力选择两条路线：
  - 对于新手来说：
    1. 将一部分原始代码粘贴到新项目
      - 推荐优先搬运物品和方块相关的部分
    2. 修复所有编译错误
    3. 修复所有运行时错误
    4. 测试这部分代码对应的功能是否正常
    5. 返回第一步，直到所有代码都被阅读和修改完毕
  - 对于熟练掌握两个mod加载器的原理，并使用两个加载器写过Mod的人来说：
    1. 将所有原始代码粘贴到新项目
    2. 修复所有编译错误，这通常还不错，因为大多数已更改的内容在新版本中都有 1:1 映射
    3. 修复运行时错误，这有点困难，因为它需要更多的测试
    4. 恢复原来的功能，这对参考链接中的网友来说是最难的部分

注意事项：
- 创建两个项目，一个从Mod的GitHub地址`git clone --depth 1 -b 1.20.1（或类似的分支名） https://github.com/example/xxx.git`下来，另一个使用fabric https://fabricmc.net/develop/template/ 生成的模板项目，而不是创建一个项目然后频繁切换git分支，因为进行移植的时候需要阅读两个项目的依赖项反编译出来的源码，如果不能同时阅读两种依赖项源码，就会导致要记住更多的东西，提高了移植难度，所以没有必要在这种地方节约存储空间
- 请使用和移植前的代码相同的mapping，也就是反编译映射，当出现需要借鉴另外的项目的源码时，推荐使用 https://linkie.shedaniel.dev/mappings 网址进行映射之间的转换
- 保持相同的ModID和包名，应当在移植完成后再考虑修改包名，因为提前修改会导致需要大量改动代码的各种地方，`import`那些的，所以一定不要先改包名再移植
- forge和fabric有很多不同的地方，forge一般用注解（`Annotation`）注册事件，fabric则使用传入接口的对象，或者说闭包（`Lambda`，`Closure`之类的）注册事件，这是应当优先修改的
- 大部分的游戏资源文件都不需要修改，除了以下地方：
  - `sounds.json`文件中，删除顶层键值对的键（例如`"block.modid.bubble_pop"`）中的`block.modid`部分，键的这一部分在fabric中是没有的
  - 配方之类的`tag`从`"forge:salts"`修改为`"fabric:salts"`（我没有仔细研究这个tag是否是正确的，应当修改为社区编写fabric mod时使用的tag）
  - 最后，所有json中，把`forge`修改为`fabric`
- mod依赖项应当确保修改为fabric版本，推荐使用modrinth的maven托管库
- 遇到问题首先查看 https://fabricmc.net/wiki/start 官方百科，搜索时，请使用关键词：`minecraft fabric wiki` + `how to`（可选） + 你的疑问
- 遇到标注`@Override`无效（会报错）时，如果有对应的类似的可覆盖的方法，就修改为覆盖那个方法，没有的话就删掉这个方法
- 遇到mod的代码中访问私有（`private protected`之类的）变量或修改固定变量（`final`）时，右键错误的部分，复制`aw Entry`，使用fabric的accessWidener修改可访问性，详见 https://fabricmc.net/wiki/tutorial:accesswideners
- 前面这些基本上都可以不花很大精力的进行操作，但是最重要的依然是阅读和理解业务逻辑，并根据代码实际的含义进行修改，而不是无脑复制粘贴
- 当某个类，例如`UseItemCallback`，不知道如何使用，并且搜索引擎给不出需要的结果时，使用 https://github.com/search 查找用法（使用 Filter by `Code`选项）
- 最麻烦的情况是Forge魔改了MineCraft的一些事件，例如`FoodData`类中的事件，这会导致就算是用mixin，也没法在同样的位置获取事件传入的参数，这时候应当先搜索对应事件如何在fabric中被监听到，然后使用Fabric自带的API注册事件监听