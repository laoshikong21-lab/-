# 我的文章网站

温暖文艺风格的个人文章网站，适合部署到 GitHub Pages。

## 📁 文件结构

```
site/
├── index.html          ← 首页（文章列表）
├── style.css           ← 全站公共样式
├── article.css         ← 文章页专用样式
├── articles/           ← 所有文章放这里
│   └── chapter2-safety-law.html
└── README.md           ← 本说明文件
```

## 🚀 部署到 GitHub Pages（一步步来）

### 第一步：注册 GitHub 账号
1. 打开 https://github.com
2. 点击 Sign Up，注册一个账号

### 第二步：创建仓库
1. 登录后，点击右上角 **+** → **New repository**
2. 仓库名填：`my-articles`（或你喜欢的名字）
3. 选择 **Public**
4. 勾选 **Add a README file**
5. 点击 **Create repository**

### 第三步：上传文件
1. 在仓库页面，点击 **Add file** → **Upload files**
2. 把整个 site 文件夹里的文件全部拖进去（注意：是文件夹 **里面** 的文件，不是文件夹本身）
3. 确保文件结构是：
   - `index.html`（在根目录）
   - `style.css`（在根目录）
   - `article.css`（在根目录）
   - `articles/chapter2-safety-law.html`（在 articles 文件夹里）
4. 点击 **Commit changes**

### 第四步：开启 GitHub Pages
1. 进入仓库 → **Settings** → 左侧栏 **Pages**
2. Source 选择 **Deploy from a branch**
3. Branch 选择 **main**，文件夹选 **/ (root)**
4. 点击 **Save**
5. 等待 1-2 分钟，页面顶部会出现你的网站链接：
   `https://你的用户名.github.io/my-articles/`

### 第五步：大功告成！
把链接发到朋友圈就能阅读了 🎉

---

## ➕ 添加新文章

### 1. 在 articles/ 文件夹创建新的 HTML 文件

复制 `articles/chapter2-safety-law.html` 作为模板，修改里面的内容。

关键要保留的结构：
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>你的文章标题</title>
  <link rel="stylesheet" href="../style.css">
  <link rel="stylesheet" href="../article.css">
</head>
<body>

  <!-- 导航（保持不变） -->
  <nav class="site-nav">
    <div class="nav-inner">
      <a href="../index.html" class="nav-brand">我的文章</a>
      <div class="nav-links">
        <a href="../index.html">首页</a>
      </div>
    </div>
  </nav>

  <!-- 修改标题区 -->
  <header class="article-hero">
    <div class="meta">2025 年 X 月 <span class="tag">分类</span></div>
    <h1>你的文章标题</h1>
    <p class="subtitle">副标题（可选）</p>
  </header>

  <!-- 文章内容 -->
  <main class="article-body">
    <div class="article-content">
      <a href="../index.html" class="back-link">← 返回文章列表</a>

      <!-- 在这里写你的文章内容 -->
      <h2>第一节</h2>
      <p>正文内容...</p>

    </div>
  </main>

  <!-- 页脚（保持不变） -->
  <footer class="site-footer">
    <div class="footer-divider"></div>
    <p class="footer-quote">学而不思则罔，思而不学则殆</p>
    <p>© 2025</p>
  </footer>

</body>
</html>
```

### 2. 在 index.html 中添加文章链接

打开 `index.html`，找到 `<!-- ====== 在这里添加新文章 ====== -->` 这行注释，在下面添加：

```html
<li class="article-item">
  <a href="articles/你的文件名.html" class="article-link">
    <div class="article-meta">
      <span class="article-date">2025 年 X 月</span>
      <span class="article-tag">分类标签</span>
    </div>
    <h2 class="article-title">文章标题</h2>
    <p class="article-desc">一两句话的文章简介。</p>
    <span class="article-arrow">阅读全文 →</span>
  </a>
</li>
```

### 3. 上传到 GitHub
在 GitHub 仓库页面，点击 Add file → Upload files，上传修改后的文件即可。

---

## 🎨 可用的样式组件

在文章中可以使用这些现成的样式：

### 彩色卡片
```html
<!-- 核心要点（金色） -->
<div class="card key">
  <div class="card-label">★ 标题</div>
  <p>内容</p>
</div>

<!-- 案例（赤陶色） -->
<div class="card case">
  <div class="card-label">🏭 标题</div>
  <p>内容</p>
</div>

<!-- 串联（绿色） -->
<div class="card link-card">
  <div class="card-label">🔗 标题</div>
  <p>内容</p>
</div>

<!-- 警告/易错点（红色） -->
<div class="card warn">
  <div class="card-label">❗ 标题</div>
  <p>内容</p>
</div>
```

### 表格
```html
<div class="table-wrap">
<table>
<thead><tr><th>列1</th><th>列2</th></tr></thead>
<tbody>
<tr><td>内容</td><td>内容</td></tr>
</tbody>
</table>
</div>
```

### 层级标签
```html
<div class="layer-badge what"><span class="icon">📖</span> 第一层：是什么</div>
<div class="layer-badge why"><span class="icon">🧠</span> 第二层：为什么</div>
<div class="layer-badge link"><span class="icon">🔗</span> 第三层：串联</div>
<div class="layer-badge practice"><span class="icon">🏭</span> 第四层：实践</div>
```
