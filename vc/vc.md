# 版本控制

### 使用token来进行git的操作认证

#####背景
*[2020 年 7 月，github要求对所有经过身份验证的 Git 操作使用基于令牌的身份验证（例如，个人访问、OAuth 或 GitHub 应用程序安装令牌）](https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/)

#####步骤
1. 登录github  https://github.com/
2. 头像（右上角）- Settings - Developer settings - Personal access tokens - Generate new token 
3. git remote set-url origin https://<your_token>@github.com/<USERNAME>/<REPO>.git




