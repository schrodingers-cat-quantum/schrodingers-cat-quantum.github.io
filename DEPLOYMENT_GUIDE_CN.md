# 零基础制作和部署个人主页

## 一、先理解五个基本概念

你现在拿到的是一个“静态网站”。它没有服务器端程序和数据库，只由浏览器能够直接读取的文件组成。

- **HTML**：网页的内容和结构。姓名、段落、论文列表、链接都写在 `index.html` 中。
- **CSS**：网页的外观。颜色、字体大小、间距、电脑与手机布局都写在 `styles.css` 中。
- **JavaScript**：网页的少量交互。本模板只用它控制深浅色、手机菜单和滚动动画，写在 `script.js` 中。
- **托管（hosting）**：把这些文件放到一台公开服务器上。GitHub Pages 就是免费的静态网站托管服务。
- **域名（domain）**：用户输入的网址。GitHub 默认给你 `用户名.github.io`；自定义 `.com` 域名通常需要单独购买。

对这个模板而言，你不需要学习服务器管理，也不需要安装 Node.js、Python、Jekyll、Hugo 或数据库。

---

## 二、发布前先修改主页

### 1. 解压文件

解压后应当直接看到 `index.html`、`styles.css` 和 `script.js`。不要只上传外层文件夹。

### 2. 修改最关键的三项

用文本编辑器或 Visual Studio Code 打开 `index.html`，使用搜索功能依次查找：

```text
YOUR-GITHUB-USERNAME
your.email@university.ac.jp
avatar-placeholder.svg
```

分别修改为：

- 你的 GitHub 用户名；
- 你准备公开的邮箱；
- 头像文件名。

### 3. 替换头像

把照片裁成接近正方形，建议 800×800 像素左右，保存为：

```text
assets/portrait.jpg
```

然后把 `index.html` 中：

```html
assets/avatar-placeholder.svg
```

改成：

```html
assets/portrait.jpg
```

同时把 `alt` 文字改为合适的照片说明。

### 4. 修改个人内容

`index.html` 中的文字就是网页正文。你可以直接修改：

- `Postdoctoral Researcher · The University of Tokyo`
- 首页简介
- About 段落
- 四个研究方向
- 论文列表
- News 列表
- Contact 信息

修改标签中间的文字即可。例如：

```html
<h3>Stochastic heat engines</h3>
```

可以改成：

```html
<h3>Finite-time thermodynamics</h3>
```

通常不要随意删除尖括号中的标签，例如 `<h3>`、`</h3>`。

### 5. 本地检查

双击 `index.html` 即可在浏览器中打开。至少检查：

- 姓名、单位和邮箱是否正确；
- 每一个论文链接是否打开正确页面；
- 手机宽度下菜单是否正常；
- 头像是否清晰；
- 是否仍然存在 `YOUR-`、`your.email`、`TODO` 或不希望公开的信息。

---

## 三、完全通过浏览器部署到 GitHub Pages

这是最适合零基础用户的方法，不需要使用命令行。

### 第 1 步：创建 GitHub 账户

注册 GitHub 账户并完成邮箱验证。假设用户名是：

```text
guohuaxu
```

那么你的默认个人主页域名将是：

```text
https://guohuaxu.github.io/
```

实际地址以你自己的用户名为准。

### 第 2 步：创建仓库

登录 GitHub 后：

1. 点击右上角 `+`。
2. 选择 `New repository`。
3. 仓库名称必须写成：

   ```text
   你的用户名.github.io
   ```

4. 选择 `Public`。
5. 可以不勾选自动添加 README，因为模板已经包含 README。
6. 点击 `Create repository`。

仓库名必须和用户名完全一致。例如用户名是 `guohuaxu`，仓库就应是 `guohuaxu.github.io`，不能写成 `homepage` 或 `my-website`。项目仓库也能发布 Pages，但网址会多一层路径；第一次建议使用用户主页仓库。

### 第 3 步：上传文件

进入新仓库后：

1. 点击 `uploading an existing file`，或者 `Add file → Upload files`。
2. 把解压后的**全部文件和 assets 文件夹**拖入上传区。
3. 确认文件列表最外层直接出现 `index.html`。
4. 在下方提交说明中填写：

   ```text
   Initial academic homepage
   ```

5. 点击 `Commit changes`。

最常见的错误是上传成：

```text
仓库 / guohua-xu-academic-homepage / index.html
```

正确结构应是：

```text
仓库 / index.html
仓库 / styles.css
仓库 / assets / ...
```

### 第 4 步：启用 GitHub Pages

1. 打开仓库上方的 `Settings`。
2. 左侧找到 `Pages`。
3. 在 `Build and deployment` 下：
   - `Source` 选择 `Deploy from a branch`；
   - `Branch` 选择 `main`；
   - 文件夹选择 `/(root)`；
   - 点击 `Save`。
4. 返回仓库的 `Actions` 或 `Settings → Pages` 查看部署状态。
5. 部署完成后，Pages 页面会显示公开网址。

首次部署可能需要短暂处理。若页面暂时显示 404，先检查 `Actions` 中的部署任务是否已经成功，再刷新网址。

### 第 5 步：以后怎样更新

最简单的方式是在 GitHub 网页上直接修改：

1. 打开 `index.html`。
2. 点击铅笔图标 `Edit this file`。
3. 修改文字。
4. 点击 `Commit changes`。
5. GitHub Pages 会自动重新发布。

替换头像或 PDF 时使用 `Add file → Upload files`，上传同名文件并提交即可。

---

## 四、使用电脑本地编辑和 Git 同步

网页内容变多以后，推荐使用 Visual Studio Code 和 GitHub Desktop。两者都有图形界面。

### GitHub Desktop 方法

1. 安装 GitHub Desktop 并登录。
2. 选择 `File → Clone repository`。
3. 选择你的 `用户名.github.io` 仓库并下载到本地。
4. 用 Visual Studio Code 打开该文件夹。
5. 修改并保存文件。
6. 回到 GitHub Desktop，填写变更说明。
7. 点击 `Commit to main`，然后点击 `Push origin`。

### 命令行方法（以后再学也可以）

```bash
git clone https://github.com/你的用户名/你的用户名.github.io.git
cd 你的用户名.github.io

# 修改文件后：
git add .
git commit -m "Update homepage"
git push
```

三个命令的意思分别是：记录修改、创建一次版本、上传到 GitHub。

---

## 五、在中国大陆访问时怎样提高可靠性

### 1. 不要依赖外部网页资源

本模板已经避免以下常见问题：

- 不使用 Google Fonts；
- 不从 `cdnjs`、`jsDelivr`、`unpkg` 等外部 CDN 加载 CSS 或 JavaScript；
- 不嵌入 YouTube、Google Maps 或 Google Analytics；
- 所有图像和代码都与网页放在同一个仓库。

因此，即使某些外部服务不可访问，主页本身仍能完整显示。论文和 Google Scholar 等外链是否可打开，则取决于对应站点。

### 2. 保留两个镜像地址

可以让同一个 GitHub 仓库同时发布到：

- GitHub Pages；
- Cloudflare Pages 或 Netlify。

这样不需要维护两套源代码。GitHub 是源文件仓库，另外的平台自动读取同一仓库；每次提交后，两边都会更新。

不过，任何境外免费二级域名都不能承诺在中国大陆永久稳定。不同省份、运营商和时期的结果可能不同。最可靠的做法是保留两个地址，并请国内不同网络的朋友实际测试。

### 3. 不建议把 Vercel 默认域名作为国内访问主地址

`vercel.app` 默认二级域名在中国大陆的可访问性通常比 GitHub Pages、Cloudflare Pages 或 Netlify 更差，因此不建议把它作为主要入口。

### 4. 自定义域名的作用和局限

以后可以买一个简短的 `.com` 或 `.net` 域名，例如：

```text
guohuaxu.com
```

优点：

- 不受 GitHub 用户名变化影响；
- 可以在不同托管平台之间切换而不更改公开网址；
- 更适合写在论文、简历和报告幻灯片中。

局限：

- 域名本身通常不是免费的；
- 使用自定义域名并不自动保证中国大陆访问；
- 若服务器或 CDN 真正部署在中国大陆，通常需要完成 ICP 备案；境外或香港节点不等于大陆备案托管。

### 5. 同一仓库部署到 Cloudflare Pages

大致流程：

1. 登录 Cloudflare。
2. 进入 `Workers & Pages`。
3. 创建 Pages 项目并连接 GitHub。
4. 选择你的主页仓库。
5. 这个模板没有构建过程：
   - Build command 留空；
   - Output / publish directory 设为仓库根目录，通常填写 `/` 或留空，按界面要求选择。
6. 部署后得到一个 `*.pages.dev` 地址。

### 6. 同一仓库部署到 Netlify

大致流程：

1. 登录 Netlify。
2. 选择从 Git 仓库导入项目。
3. 连接 GitHub 并选择主页仓库。
4. Build command 留空。
5. Publish directory 设为仓库根目录，通常填写 `.`。
6. 部署后得到一个 `*.netlify.app` 地址。

也可以直接把整个网站文件夹拖入 Netlify 的手动部署界面，但这种方式不会随 GitHub 自动更新。

---

## 六、自定义域名连接 GitHub Pages

购买域名以后：

1. 在 GitHub 仓库 `Settings → Pages → Custom domain` 输入域名。
2. 根据 GitHub 显示的要求，在域名注册商处添加 DNS 记录。
3. 等待 DNS 生效。
4. 勾选 `Enforce HTTPS`。
5. GitHub 通常会在仓库根目录生成 `CNAME` 文件。

本项目附有 `CNAME.example`。在没有购买和配置域名之前不要把它改名为 `CNAME`，否则可能导致默认 Pages 地址异常。

---

## 七、常见故障

### 打开网址显示 404

依次检查：

- 仓库是否为 `用户名.github.io`；
- 仓库是否公开；
- `index.html` 是否在最外层；
- `Settings → Pages` 是否选择 `main` 和 `/(root)`；
- `Actions` 中 Pages 部署是否成功；
- 网址中的用户名大小写和拼写是否正确。

### 网页有文字但没有样式

通常是 `styles.css` 没上传，或者文件被放在多余的子文件夹中。确认 `index.html` 与 `styles.css` 位于同一级。

### 头像不显示

确认：

- 图片确实在 `assets` 文件夹；
- 文件名和扩展名完全一致；
- Linux 服务器区分大小写，例如 `Portrait.jpg` 与 `portrait.jpg` 是两个不同文件。

### 修改后仍显示旧内容

- 先确认新的 commit 已经提交；
- 检查 Pages 部署是否完成；
- 浏览器执行强制刷新：Mac 通常是 `Command + Shift + R`，Windows 通常是 `Ctrl + F5`；
- 也可以用无痕窗口打开。

### 中国大陆部分网络打不开

这不一定是代码错误。用不同运营商、不同省份和手机流量测试；同时准备 GitHub Pages 与另一个镜像地址。不要通过加入更多境外 CDN 来“加速”，否则可能增加新的不可访问依赖。

---

## 八、下一阶段最值得学习的内容

按下面顺序即可，不需要一开始系统学习前端工程：

1. HTML：标题、段落、链接、图片、列表和 section。
2. CSS：选择器、颜色、间距、Flexbox、Grid 和媒体查询。
3. Git：commit、push、pull 和版本回退。
4. 域名与 DNS：A、AAAA、CNAME 记录以及 HTTPS。
5. 当主页内容很多时，再考虑 Jekyll、Hugo 或 Astro 等静态网站生成器。

这个模板足以长期维护一个正常的学术个人主页；只有在需要频繁写博客、自动生成论文列表或管理几十个页面时，才有必要换用更复杂的工具。
