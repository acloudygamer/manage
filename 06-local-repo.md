# 本地仓库创建与推送

## 从零创建仓库

### 方式一：使用 gh（推荐）

```bash
# 1. 进入目录
cd D:/your/project
D:

# 2. 初始化 Git
git init

# 3. 添加文件
git add -A

# 4. 提交
git commit -m "Initial commit"

# 5. 创建并推送
gh repo create my-repo --public --source=. --push
```

### 方式二：手动关联

```bash
# 1. 进入目录
cd D:/your/project
D:

# 2. 初始化
git init

# 3. 手动创建远程仓库后，关联
git remote add origin https://github.com/username/my-repo.git

# 4. 添加文件并提交
git add -A
git commit -m "Initial commit"

# 5. 推送
git push -u origin main
```

## 重新绑定远程仓库

```bash
# 1. 查看当前远程仓库
git remote -v

# 2. 移除旧远程仓库
git remote remove origin

# 3. 添加新的远程仓库
git remote add origin https://github.com/username/new-repo.git

# 4. 推送到新仓库
git push -u origin main
```

## 常用操作

```bash
# 查看状态
git status

# 查看远程仓库信息
git remote -v

# 提交修改
git add -A
git commit -m "提交信息"
git push origin main

# 拉取更新
git pull origin main
```
