# Git 基础

## 工作区、暂存区、仓库

Git 中有三个核心概念：
- **工作区**：本地文件系统中的文件目录
- **暂存区（Stage）**：即将提交的文件列表
- **仓库**：存储提交历史的地方，分为本地仓库和远程仓库

## 基本工作流程

```bash
# 1. 查看状态
git status

# 2. 添加到暂存区
git add <file_name>    # 添加单个文件
git add -A             # 添加所有文件

# 3. 提交到仓库
git commit -m "提交信息"

# 简写：暂存 + 提交（仅适用于已跟踪的文件）
git commit -a -m "提交信息"
```

## 查看差异

```bash
# 查看工作区与暂存区的差异
git diff

# 查看暂存区与仓库的差异
git diff --cached

# 查看工作区与仓库的差异
git diff HEAD
```

## 查看提交历史

```bash
# 查看详细提交历史
git log

# 查看简洁提交历史
git log --oneline

# 查看最近N条提交
git log -n
```
