# GitHub CLI

GitHub CLI (`gh`) 是官方命令行工具，可以在不登录 GitHub 网页的情况下操作仓库。

## 基础操作

```bash
# 登录
gh auth login

# 查看登录状态
gh auth status
```

## 克隆仓库

```bash
# 使用 gh 克隆仓库
gh repo clone username/repository

# 克隆到指定目录
gh repo clone username/repository D:/path/to/directory
```

## 创建仓库

```bash
# 在当前目录创建公开仓库并推送
gh repo create my-repo --public --source=. --push

# 创建私有仓库
gh repo create my-repo --private --source=. --push

# 从零创建（不基于现有目录）
gh repo create my-repo --public
```

## 其他常用命令

```bash
# 查看仓库信息
gh repo view

# 创建 Issue
gh issue create --title "Bug" --body "描述"

# 创建 Pull Request
gh pr create --title "Feature" --body "描述"

# 查看 PR 列表
gh pr list
```

## 使用 gh 免登录创建仓库完整流程

```bash
# 1. 进入目录
cd D:/your/project
D:

# 2. 初始化 Git（如果尚未初始化）
git init

# 3. 添加所有文件
git add -A

# 4. 提交代码
git commit -m "Initial commit"

# 5. 创建并推送仓库
gh repo create my-repo --public --source=. --push
```
