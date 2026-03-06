# PulmoMask 部署与本地运行（中文）

本文档对应 GitHub.io **User Page**（仓库名固定：`pulmomask.github.io`）部署方式。

## 0) 先改配置

请先编辑 `_config.yml`：

- `url`: 改为 `https://pulmomask.github.io`
- `baseurl`: 设为空字符串 `""`

例如：

- `url: https://pulmomask.github.io`
- `baseurl: ""`

## 1) 推荐：Docker 本地预览（最不污染全局环境）

在项目根目录运行：

```bash
docker compose pull
docker compose up
```

浏览器打开：`http://localhost:8080`

停止：

```bash
docker compose down
```

## 2) 可选：本地隔离环境（不用全局 gem）

> 只有在你明确希望不用 Docker 时再走这一条。

```bash
# Python 隔离环境（仅供本项目使用）
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# Bundler 安装到仓库内，不写全局目录
bundle config set --local path 'vendor/bundle'
bundle install

# 本地启动
bundle exec jekyll serve --livereload --port 8080
```

如果提示 Bundler 版本不匹配，请先安装对应版本（按报错提示的版本号）。

## 3) GitHub Pages 自动部署

该模板已自带 `.github/workflows/deploy.yml`，推送到 `main`/`master` 会自动构建并发布。

### 操作步骤

1. 将本地仓库推送到 GitHub（仓库名必须：`pulmomask.github.io`）。
2. 在 GitHub 仓库设置中确认：
   - `Actions` 权限允许工作流写入仓库内容（`Read and write permissions`）。
3. 推送一次修改（触发 Deploy workflow）。
4. 工作流成功后，确认 Pages 来源：
   - `Settings` → `Pages` → Source 选择 `Deploy from a branch`
   - Branch 选择 `gh-pages`，目录选择 `/ (root)`
5. 等待 1~5 分钟后访问：
   - `https://pulmomask.github.io/`

## 4) 常见问题

- 页面无样式：通常是 `url/baseurl` 配置错误。
- 404：首次部署时 `gh-pages` 分支可能还未生成，稍等工作流完成。
- 本地 Ruby 报错：优先改用 Docker 方案。
