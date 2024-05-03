参考
- https://www.reddit.com/r/feedthebeast/comments/102jpqk/comment/j2xom9w/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button
- 

1. 创建新项目，保持相同的ModID和包名等
2. 修复gradle fabric loom依赖项问题
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
    4. 恢复原来的功能，这对我来说是最难的部分