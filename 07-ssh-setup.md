# GitHub 令牌认证

GitHub 令牌（Personal Access Token）是推荐的身份验证方式，比 SSH 更简单。

## 生成令牌

1. 登录 GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. 点击 "Generate new token"
3. 勾选需要的权限（如 repo）
4. 生成后复制令牌

## 使用令牌

令牌可以作为密码使用：

```bash
# 克隆时输入用户名，令牌作为密码
git clone https://github.com/username/repo.git
```

## 配置凭证存储

```bash
# 自动保存凭证
git config --global credential.helper store
```

## 无需代理

使用 GitHub 令牌时，国内通常可直接访问，无需配置代理。
