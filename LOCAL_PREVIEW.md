# Academic Pages 本地改版

本网站直接使用旁边 `academicpages.github.io` 仓库的 Jekyll 模板；原有内容已迁入主页及 Publications、Experience、Projects、Reading notes 页面。

## 本地运行

需要 Ruby 3.4 及 Bundler（与发布工作流一致）。在仓库目录中运行：

```bash
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve --config _config.yml,_config_local.yml --host 127.0.0.1 --port 4000
```

打开 http://localhost:4000 。按 Ctrl+C 停止。

## 修改内容

- `index.html`：简介、研究方向、海报条目、个人兴趣。
- `_pages/`：会议海报、经历与教育、六个项目、三份阅读笔记。
- `_config.yml`：个人资料、公开网站地址与主题。
- `_data/navigation.yml`：顶部菜单。
- `assets/css/custom.css`：项目列表和履历条目的少量排版。
- `HeyuanCV_2026.pdf`：沿用现有 CV。

原有 42 个文件均保留，旧首页原文另存于 `original/index.html`，该目录不参与网站构建。所有原有图片、PDF 和演示文稿保持原路径。Academic Pages 的演示文章、虚构论文、默认个人资料没有加入你的网站。

本次未提交、推送或部署。以后是否发布由你决定；此说明不修改 GitHub 上的配置。

模板来源：Academic Pages，本地模板版本 `7b958332ce9970cfb6987a049d7684ac615397e8`。保留其 MIT LICENSE。

## 首次发布

本地已准备 `.github/workflows/pages.yml`。你推送到 `main` 后，该工作流会用 Ruby 3.4 和锁定的依赖生成网站，再发布到 GitHub Pages。

1. 打开 https://github.com/MiSFiT5/MiSFiT5.github.io/settings/pages 。
2. 在 **Build and deployment → Source** 中选择 **GitHub Actions**。已有工作流，无需再点模板的 Configure。
3. 在本地网站目录中依次运行：

```bash
cd /Users/heliu/Desktop/Personal/MiSFiT5.github.io
git status
git add .
git commit -m "Migrate personal website to Academic Pages"
git push origin main
```

4. 打开 https://github.com/MiSFiT5/MiSFiT5.github.io/actions ，查看 **Deploy personal website** 最近一次运行。
5. 等 `build` 和 `deploy` 都成功后，访问 https://misfit5.github.io/ 。

此工作流仅在你推送 `main` 或手动运行时发布。本次准备未提交、推送，也未修改 GitHub 设置。实际 GitHub 构建与发布需由首次运行验证。
