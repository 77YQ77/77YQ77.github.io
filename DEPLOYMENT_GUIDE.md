# 学术网站制作和部署指南

基于 Jon Barron 的学术网站模板，制作你自己的学术主页。

## 📋 网站结构

你的网站已经包含以下核心文件：

```
jonbarron.github.io-master/
├── index.html          # 主页面（已修改为 Yao Hu 的信息）
├── stylesheet.css      # 样式文件
├── images/             # 图片和视频文件夹
│   └── YaoHu.jpg      # 你的照片（需要添加）
├── data/               # 数据文件（可选）
└── CNAME              # 自定义域名（可选）
```

## 🎨 核心功能说明

### 1. 图片 Hover 效果

网站使用 CSS 和 JavaScript 实现图片悬停效果：

```html
<div class="one">
  <div class="two" id='paper_image'>
    <video width=100% muted autoplay loop>
      <source src="images/paper_video.mp4" type="video/mp4">
    </video>
  </div>
  <img src='images/paper_image.jpg' width=100%>
</div>
<script>
  function paper_start() {
    document.getElementById('paper_image').style.opacity = "1";
  }
  function paper_stop() {
    document.getElementById('paper_image').style.opacity = "0";
  }
  paper_stop()
</script>
```

**工作原理：**
- `.one` 和 `.two` 类实现图片叠加
- 鼠标悬停时，视频/第二张图片淡入显示
- 使用 CSS transition 实现平滑过渡

### 2. 论文条目格式

每个论文条目的标准格式：

```html
<tr bgcolor="#ffffd0">  <!-- 高亮重要论文 -->
  <td style="padding:16px;width:20%;vertical-align:middle">
    <!-- 图片/视频区域 -->
  </td>
  <td style="padding:8px;width:80%;vertical-align:middle">
    <span class="papertitle">论文标题</span>
    <br>
    <strong>Yao Hu</strong>, 其他作者
    <br>
    <em>期刊/会议名称</em>, 年份
    <br>
    <a href="论文链接">paper</a> /
    <a href="代码链接">code</a> /
    <a href="bibtex链接">bibtex</a>
  </td>
</tr>
```

## 🚀 部署到 GitHub Pages

### 方法 1: 使用 GitHub Pages（推荐）

1. **创建 GitHub 仓库**
   - 登录 GitHub
   - 点击 "New repository"
   - 仓库名：`yourusername.github.io`（例如：`yaohu.github.io`）
   - 设置为 Public
   - 不要初始化 README

2. **上传文件**
   ```bash
   # 在项目目录下执行
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/yourusername.github.io.git
   git push -u origin main
   ```

3. **启用 GitHub Pages**
   - 进入仓库 Settings
   - 找到 Pages 选项
   - Source 选择 "Deploy from a branch"
   - Branch 选择 "main" 和 "/ (root)"
   - 点击 Save

4. **访问网站**
   - 几分钟后，访问：`https://yourusername.github.io`

### 方法 2: 使用自定义域名

1. **购买域名**（可选）
   - 在域名注册商购买（如 Namecheap, GoDaddy）

2. **配置 CNAME 文件**
   - 在项目根目录创建/编辑 `CNAME` 文件
   - 内容：`yourdomain.com`

3. **配置 DNS**
   - 在域名注册商添加 DNS 记录：
     - Type: CNAME
     - Name: @ 或 www
     - Value: yourusername.github.io

4. **在 GitHub 设置**
   - 仓库 Settings → Pages
   - Custom domain 填入你的域名

## 📝 需要完成的步骤

### 1. 添加照片
- 将照片文件放到 `images/` 文件夹
- 命名为 `YaoHu.jpg`
- 建议尺寸：正方形，至少 400x400 像素

### 2. 添加论文图片
- 为每篇论文准备一张预览图
- 放到 `images/` 文件夹
- 在 HTML 中引用：`images/paper_name.jpg`

### 3. 添加论文链接
- 为每篇论文添加：
  - Paper 链接（arXiv 或期刊链接）
  - Code 链接（如果有 GitHub 仓库）
  - BibTeX 链接（可选）

### 4. 清理旧内容
- 删除所有旧的论文条目（Jon Barron 的论文）
- 确保只保留你的论文

## 🎯 改进建议

参考 https://xminghsueh.github.io/ 的设计，可以添加：

1. **论文分类**
   ```html
   <h2>Medical Image Analysis</h2>
   <!-- 相关论文 -->
   <h2>Federated Learning</h2>
   <!-- 相关论文 -->
   ```

2. **更多链接**
   - 为每篇论文添加 code、bibtex 链接
   - 添加项目页面链接

3. **视频预览**
   - 为重要论文添加视频预览
   - 使用 hover 效果展示

## 📚 参考资源

- [Jon Barron 的网站源码](https://github.com/jonbarron/jonbarron.github.io)
- [GitHub Pages 文档](https://docs.github.com/en/pages)
- [Xiaoming Xue 的网站](https://xminghsueh.github.io/) - 另一个很好的参考

## ✅ 检查清单

- [ ] 照片已添加到 `images/YaoHu.jpg`
- [ ] 所有个人信息已更新
- [ ] 所有论文信息已添加
- [ ] 论文图片已准备
- [ ] 旧内容已清理
- [ ] 代码已推送到 GitHub
- [ ] GitHub Pages 已启用
- [ ] 网站可以正常访问

## 🆘 常见问题

**Q: 网站显示 404？**
A: 等待几分钟让 GitHub Pages 部署完成，或检查仓库设置。

**Q: 图片不显示？**
A: 检查图片路径是否正确，确保图片文件已上传到 GitHub。

**Q: 样式不生效？**
A: 确保 `stylesheet.css` 文件存在且路径正确。

**Q: 如何更新网站？**
A: 修改文件后，提交并推送到 GitHub，几分钟后自动更新。

