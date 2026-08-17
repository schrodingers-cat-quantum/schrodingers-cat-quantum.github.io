# Guo-Hua Xu Academic Homepage

这是一个可以直接部署到 GitHub Pages 的纯静态学术个人主页。它只使用 HTML、CSS 和少量 JavaScript，没有构建工具、数据库、外部字体、第三方 CDN 或追踪代码。

## 文件结构

```text
.
├── index.html                 # 网页内容：姓名、简介、研究、论文、联系方式
├── styles.css                 # 网页样式：颜色、排版、手机适配
├── script.js                  # 深浅色切换、手机菜单、滚动动画
├── 404.html                   # 无效地址页面
├── robots.txt                 # 搜索引擎规则
├── .nojekyll                  # 让 GitHub Pages 按普通静态文件发布
├── CNAME.example              # 自定义域名示例，暂时不要改名
├── DEPLOYMENT_GUIDE_CN.md     # 零基础部署和修改说明
└── assets/
    ├── avatar-placeholder.svg # 头像占位图
    ├── research-spectrum.svg  # 首页研究主题装饰图
    ├── social-card.svg        # 分享链接时使用的预览图
    └── favicon.svg            # 浏览器标签图标
```

## 发布前必须修改的内容

在 `index.html` 中搜索以下文字并替换：

1. `YOUR-GITHUB-USERNAME`：换成你的 GitHub 用户名。
2. `your.email@university.ac.jp`：换成公开使用的邮箱。
3. 检查姓名、职位、单位、个人简介、研究方向、论文和新闻。
4. 用个人照片替换 `assets/avatar-placeholder.svg`。最简单的做法是把照片命名为 `portrait.jpg`，放入 `assets` 文件夹，然后把 `index.html` 中两处 `assets/avatar-placeholder.svg` 改成 `assets/portrait.jpg`。

主页中的 Google Scholar 链接已经设置为 Guo-Hua Xu 的公开学术主页。其余信息仍应在正式发布前逐项确认。

## 最简单的本地预览

不需要安装任何软件：双击 `index.html`，浏览器会直接打开网页。

更推荐使用 Visual Studio Code 打开整个文件夹。安装 VS Code 的 “Live Server” 扩展后，右键 `index.html`，选择 “Open with Live Server”，修改后浏览器会自动刷新。

## GitHub Pages 部署

完整步骤请看 [`DEPLOYMENT_GUIDE_CN.md`](DEPLOYMENT_GUIDE_CN.md)。核心要求是：

- 仓库名称使用 `<你的用户名>.github.io`；
- `index.html` 必须位于仓库最外层，而不是再套一层文件夹；
- 在仓库 `Settings → Pages` 中选择 `Deploy from a branch`；
- 分支选 `main`，目录选 `/(root)`。

部署成功后，地址通常是：

```text
https://你的用户名.github.io/
```

## 添加 CV

把个人简历 PDF 命名为 `cv.pdf`，放在项目根目录。然后在 `index.html` 中搜索：

```html
<!-- <p><a class="text-link" href="cv.pdf">Download my CV →</a></p> -->
```

删除开头的 `<!--` 和结尾的 `-->` 即可显示链接。

## 许可

网页代码采用 MIT License。个人简介、照片、论文信息等个人内容不自动授权他人使用。
