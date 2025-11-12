# 星尘记事 · Astro + Decap CMS 最小可行版本

这是一个使用 [Astro](https://astro.build) 与 [Decap CMS](https://decapcms.org) 构建的个人博客最小实现，目标部署平台为 [Vercel](https://vercel.com)。项目没有引入现成主题，而是基于简洁的卡片式排版打造了一个初版主题，后续可以在此基础上持续迭代。

## 本地开发

1. 安装依赖：
   ```bash
   npm install
   ```
2. 启动开发服务器：
   ```bash
   npm run dev
   ```
3. 打开浏览器访问 `http://localhost:4321` 查看站点。

Decap CMS 后台入口位于 `/admin/`，需要结合 Git 身份验证或 Netlify Identity 才能写入内容。默认配置指向 `git-gateway`，可在 `public/admin/config.yml` 中按需调整为 GitHub、GitLab 等后端。

## 内容结构

- 文章内容存放于 `src/content/posts/`，使用 Astro Content Collections 管理结构化前言。
- `public/admin/` 提供 Decap CMS 编辑器与配置文件。
- 自定义主题样式集中在 `src/styles/global.css`。

## 部署到 Vercel

1. 将仓库推送到 GitHub/GitLab。
2. 在 Vercel 新建项目并导入仓库。
3. 构建命令：`npm run build`
4. 输出目录：`dist`

Astro 已通过 `@astrojs/vercel` 适配器配置为 serverless 输出，Vercel 将自动识别并完成部署。

## 下一步规划

- 丰富主题组件（如文章目录、主题色切换等）。
- 接入 RSS、站点地图等扩展功能。
- 优化 CMS 草稿预览与多语言支持。
