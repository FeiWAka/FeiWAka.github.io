# 🚀 GitHub Pages 个人主页部署指南

用 GitHub 免费托管个人主页,域名 `https://你的用户名.github.io`。
本文件夹里 `index.html` 就是现成模板,改完直接部署。

---

## 方式一:纯网页操作(不用代码,推荐新手)⭐

> 全程在浏览器里完成,不需要安装任何东西。

### 第 1 步:注册 / 登录 GitHub
打开 https://github.com ,注册账号。记下你的**用户名**(比如 `wakaka`)。
> ⚠️ 主页地址 = 用户名.github.io,所以用户名就是你的网址,想好再注册。

### 第 2 步:创建仓库(名字必须是 用户名.github.io)
1. 登录后点右上角 `+` → `New repository`
2. **Repository name 填**:`你的用户名.github.io`
   - 例:用户名是 `wakaka`,就填 `wakaka.github.io`
3. 选 **Public**(必须公开,免费托管的前提)
4. 勾选 `Add a README file`(方便后面编辑)
5. 点绿色按钮 `Create repository`

### 第 3 步:上传主页文件
1. 进入刚建的仓库,点 `Add file` → `Upload files`
2. 把电脑上的 `index.html`(本文件夹里这个)拖进去
3. 点 `Commit changes` 提交

### 第 4 步:开启 Pages(让网站上线)
1. 进仓库 → `Settings`(设置)→ 左侧菜单点 `Pages`
2. **Build and deployment** → Source 选 `Deploy from a branch`
3. Branch 选 `main` + `/ (root)`,点 `Save`
4. 等 1-2 分钟,页面顶部会出现你的网址:`https://你的用户名.github.io`
5. 手机电脑都能访问 🎉

---

## 方式二:本地 git 推送(适合以后持续更新)

你电脑 git 已装好,用户名邮箱也配好了,直接:

```bash
cd E:\claw\projects\personal-site

# 1. 初始化仓库
git init

# 2. 加文件、提交
git add index.html
git commit -m "我的个人主页"

# 3. 关联远程仓库(换成你的仓库地址)
git remote add origin https://github.com/你的用户名/你的用户名.github.io.git

# 4. 推送
git branch -M main
git push -u origin main
```

以后每次改完主页,重复:
```bash
git add .
git commit -m "更新内容"
git push
```
等 1-2 分钟,网站自动更新。

---

## 修改模板(必看)

打开 `index.html`,用记事本/VS Code 搜索替换这几处:

| 搜索 | 替换成 |
|---|---|
| `菲菲` | 你的名字 |
| `你的邮箱@example.com` | 你的邮箱 |
| `你的GitHub用户名` | 你的 GitHub 用户名 |
| `你的uid` | 你的 B站 uid(没有就删掉那行) |

项目卡片、技能、介绍文字都可以随意改,想加项目就复制一个 `<div class="card">...</div>` 块。

---

## 常见问题

**Q: 访问显示 404?**
A: ① 仓库名必须和 用户名.github.io 完全一致 ② 开启 Pages 后要等 1-2 分钟 ③ 文件必须是 `index.html`(小写)。

**Q: 国内访问 github.io 慢/打不开?**
A: GitHub Pages 在国内偶尔不稳定,这是正常现象。备选方案:
- **Gitee Pages**(码云,国内快):把仓库推到 Gitee,同样开 Pages
- **Cloudflare Pages / Vercel**:免费且国内相对稳,连 GitHub 仓库自动同步

**Q: 想用自己的域名?**
A: 买域名后在仓库 `Settings → Pages → Custom domain` 填域名,再按提示加 DNS 记录。

---

## 本文件夹内容

```
personal-site/
├── index.html      ← 主页模板(白色简约风,自适应手机/电脑)
├── 主页预览.png    ← 模板效果预览图
└── README.md       ← 本部署指南
```
