#### 01、解决gitflow无法正常使用

1. 点击 设置 -> 编辑配置文件

2. 修改配置选项：

   ```bash
   [gitflow "prefix"]
       feature = feature/
       bugfix = bugfix/
       release = release/
       hotfix = hotfix/
       support = support/
       versiontag = 
   ```