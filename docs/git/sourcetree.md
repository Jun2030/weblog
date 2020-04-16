#### x01、安装跳过注册安装

1. 安装SrouceTree，下载地址: [https://www.sourcetreeapp.com/](https://www.sourcetreeapp.com/)，执行到选择bitbucket的界面退出

2. 到 `C:\Users\{用户名}\AppData\Local\Atlassian\SourceTree\` 这个路径下创建 `accounts.json`,并写入以下代码

   ```json
   [
     {
       "$id": "1",
       "$type": "SourceTree.Api.Host.Identity.Model.IdentityAccount, SourceTree.Api.Host.Identity",
       "Authenticate": true,
       "HostInstance": {
         "$id": "2",
         "$type": "SourceTree.Host.Atlassianaccount.AtlassianAccountInstance, SourceTree.Host.AtlassianAccount",
         "Host": {
           "$id": "3",
           "$type": "SourceTree.Host.Atlassianaccount.AtlassianAccountHost, SourceTree.Host.AtlassianAccount",
           "Id": "atlassian account"
         },
         "BaseUrl": "https://id.atlassian.com/"
       },
       "Credentials": {
         "$id": "4",
         "$type": "SourceTree.Model.BasicAuthCredentials, SourceTree.Api.Account",
         "Username": "",
         "Email": null
       },
       "IsDefault": false
     }
   ]
   ```

3. 打开 `SourceTree.exe_Url_iayhtc13zv3obzuz5vchezjs1az2q5ef` (该目录与版本有关，可能不一致)，进入 `user.config` 文件，增加以下代码

   ```basic
   <setting name="AgreedToEULA" serializeAs="String">
       <value>True</value>
   </setting>
   <setting name="AgreedToEULAVersion" serializeAs="String">
       <value>20160201</value>
   </setting>
   ```

4. 重新点击 SourceTree.exe 安装，弹框选择最后一项 [我不想使用Mercuial] 即可



#### 02、设置 SSH

1. [工具] -> [选项] -> [SSH客户端配置]
   1. [SSH客户端] 选择 [OpenSSH]
   2. [SSH密钥] 选择本地的 `id_rsa` 私钥文件（Git章节有详细教程）
2. 添加公钥到服务器，以GitHub为例：
   1. [github] -> [Settings] -> [SSH and GPG keys] -> [New SSH key] 添加 `~/.ssh/id_rsa.pub` 文件内容到里面



#### 03、账户验证

1. Basic 验证

   填写对应的用户名和密码即可验证

2. OAuth 验证

   [github] -> [Settings] -> [Developer settings] -> [OAuth Apps] 应用的名称随便填，主页 URL 填写`http://localhost:8080`，跳转网址填写 `http://localhost:8080/oauth/redirect`



