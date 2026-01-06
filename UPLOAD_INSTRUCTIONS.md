# 上传文件到 GitHub 的步骤

根据你的仓库 `Yao-Hu.github.io`，按照以下步骤操作：

## 方法 1: 使用 Git 命令行（推荐）

### 步骤 1: 初始化 Git 仓库
```bash
git init
```

### 步骤 2: 添加所有文件
```bash
git add .
```

### 步骤 3: 提交文件
```bash
git commit -m "Initial commit: Yao Hu academic website"
```

### 步骤 4: 设置主分支
```bash
git branch -M main
```

### 步骤 5: 连接远程仓库
```bash
git remote add origin https://github.com/77YQ77/Yao-Hu.github.io.git
```

### 步骤 6: 推送文件
```bash
git push -u origin main
```

## 方法 2: 使用 GitHub Desktop（图形界面）

1. 下载并安装 [GitHub Desktop](https://desktop.github.com/)
2. 登录你的 GitHub 账号
3. 点击 "File" → "Add Local Repository"
4. 选择当前文件夹
5. 点击 "Publish repository"
6. 选择仓库 `Yao-Hu.github.io`
7. 点击 "Publish Repository"

## 方法 3: 使用网页上传（适合小文件）

1. 进入仓库页面：https://github.com/77YQ77/Yao-Hu.github.io
2. 点击 "uploading an existing file"
3. 拖拽文件到页面
4. 点击 "Commit changes"

**注意：** 网页上传不适合大量文件，建议使用方法 1 或 2。

## 常见问题

**Q: 提示需要身份验证？**
A: 使用 Personal Access Token 代替密码，或使用 GitHub Desktop。

**Q: 文件太大上传失败？**
A: 检查是否有大文件（>100MB），考虑使用 Git LFS 或删除不必要的大文件。

**Q: 如何更新文件？**
A: 修改文件后，执行：
```bash
git add .
git commit -m "Update website"
git push
```

