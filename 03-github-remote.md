# GitHub 远程操作

## Fork 并克隆项目

### 1. Fork 项目

登录 GitHub，找到目标项目，点击 "Fork" 按钮创建副本到自己的仓库。

### 2. 克隆到本地

```bash
# 克隆到指定目录
git clone https://github.com/.git

# your-username/repository克隆到指定目录
git clone https://github.com/your-username/repository.git D:/path/to/directory
```

## 远程仓库操作

```bash
# 查看远程仓库
git remote -v

# 添加远程仓库
git remote add origin https://github.com/username/repo.git

# 移除远程仓库
git remote remove origin

# 修改远程仓库地址
git remote set-url origin new-url.git

# 推送到远程
git push origin main

# 拉取远程更新
git pull origin main

# 拉取远程更新（变基模式）
git pull --rebase origin main
```

## 常见问题

### 连接问题

国内访问 GitHub 通常无需代理，直连即可。
