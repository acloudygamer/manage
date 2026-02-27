# 分支管理

## 创建分支

```bash
# 创建新分支（会复制当前分支内容）
git branch dev

# 创建并切换到新分支
git switch -c dev
# 或
git checkout -b dev
```

## 切换分支

```bash
# 切换到已有分支（推荐）
git switch dev

# 旧命令（仍可用）
git checkout dev
```

## 合并分支

```bash
# 1. 切换到目标分支（通常是主分支）
git switch main

# 2. 拉取最新代码
git pull origin main

# 3. 合并分支
git merge dev

# 4. 解决冲突后，添加并提交
git add -A
git commit -m "Merge branch 'dev' into main"

# 5. 推送到远程
git push origin main
```

## 删除分支

```bash
# 删除已合并的分支
git branch -d dev

# 强制删除分支（未合并）
git branch -D dev
```

## 变基（Rebase）

变基是将提交"重新播放"到另一个分支上，可以保持提交历史线性清晰。

```bash
# 将 dev 分支变基到 main 分支
git switch dev
git rebase main
```

### 变基的原理

1. Git 会保存 dev 分支的所有提交
2. 移动 dev 的基到 main 的最新提交
3. 在 main 上重新应用 dev 的提交

### 注意事项

- **不要对已推送到远程的分支进行变基**，会修改提交历史
- 变基会重写提交历史，协作开发时需谨慎
- 个人开发中使用变基可以让历史更清晰

## 解决合并冲突

当两个分支修改了同一个文件的同一行时，会发生冲突。

```bash
# 1. 查看冲突文件
git status

# 2. 查看冲突内容
git diff

# 3. 手动编辑冲突文件，选择需要保留的内容

# 4. 标记冲突已解决
git add -A

# 5. 完成提交
git commit -m "Resolve merge conflict"
```

## 暂存工作进度

当需要临时切换分支但不想提交当前工作时，可以使用 stash。

```bash
# 保存当前工作进度
git stash save "工作进度描述"

# 查看暂存列表
git stash list

# 恢复并删除最近暂存
git stash pop

# 恢复指定暂存（不删除）
git stash apply stash@{0}

# 删除最近暂存
git stash drop

# 清空所有暂存
git stash clear
```

## 版本回退

### reset 命令

```bash
# 回退到上一个提交（mixed模式，默认）
git reset HEAD~1

# 三种模式的区别：
# --soft：只移动 HEAD 指针，不修改暂存区和工作区
# --mixed（默认）：移动 HEAD，重置暂存区，保留工作区
# --hard：移动 HEAD，重置暂存区和工作区，完全丢弃修改
git reset --hard HEAD~1
```

### reflog 恢复误操作

```bash
# 查看 HEAD 移动历史
git reflog

# 恢复到指定状态
git reset HEAD@{n}
```

## 恢复文件

```bash
# 从仓库恢复文件到工作区
git restore file.txt
git restore .

# 从某个分支恢复文件
git restore --source=dev file.txt

# 从某个提交恢复文件
git restore --source=HEAD~1 file.txt
```
