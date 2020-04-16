#### 01、github访问加速

1. 打开 [Netlify]() 官网 -> [注册] -> 关联 GitHub 登录 -> [New site from Git] -> 选择GitHub 
2. 进入Github的认证授权页面，点击 `Authorize Netlify by Netlify`
3. 点击 `All repositories` 直接选择授权所有仓库，这个授权在设置中可以改
4. 选择一个项目 如果是 docsify 项目，选择 `Base directory` 为 `/docs` 点击 [Deploy site] 发布即可
5. 部署完成后，Netlify会自动生成一个随机的二级域名 `xxx.netlify.com`，点击[Site Settings]可以修改为自定义的二级域名
6. Site details下点击[Change site name]，可以为这个站点设置一个自定义的名字



#### 02、账户验证

1. Basic 验证

   填写对应的用户名和密码即可验证。

2. OAuth 验证，e.g. SourceTee验证用户方式之一

   [github] -> [Settings] -> [Developer settings] -> [OAuth Apps] 应用的名称随便填，主页 URL 填写`http://localhost:8080`，跳转网址填写 `http://localhost:8080/oauth/redirect`。

3. Token 验证，e.g. Webstorm 登录github方式之一

   [github] -> [Settings] -> [Developer settings] -> [Personal access tokens] 生成新的token，用token登录即可。

