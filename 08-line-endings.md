# 换行符问题

## 常见问题

在 Windows 和 Linux/Mac 之间协作时，可能遇到换行符不一致的问题：

```
warning: in the working copy of 'file', LF will be replaced by CRLF
```

## 解决方案

### 方案一：配置 Git 全局换行符

```bash
# 禁用自动转换（推荐跨平台项目）
git config --global core.autocrlf false

# 强制使用 LF
git config --global core.eol lf
```

### 方案二：VSCode 设置

1. 按 `Ctrl + Shift + P`
2. 输入 "Change End of Line Sequence"
3. 选择 "LF"

### 方案三：创建 .gitattributes 文件

在仓库根目录创建 `.gitattributes` 文件：

```gitattributes
* text=auto eol=lf

*.txt text eol=lf
*.md text eol=lf
*.py text eol=lf
*.js text eol=lf
```
