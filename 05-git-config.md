# Git 配置

## 基础配置

```bash
# 设置用户名
git config --global user.name "your-name"

# 设置邮箱
git config --global user.email "your-email@example.com"

# 查看配置
git config --list
git config --global --list
```

## 网络连接

国内访问 GitHub 通常无需代理，直连即可。

如遇连接问题，可尝试配置代理：

```bash
# 设置代理
git config --global http.proxy http://127.0.0.1:7890
git config --global https.proxy http://127.0.0.1:7890

# 取消代理
git config --global --unset http.proxy
git config --global --unset https.proxy
```
