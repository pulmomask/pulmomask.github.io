# PulmoMask 项目网站

武汉大学大学生创新训练计划项目公开展示页：

**基于热电-气流反演模型的可穿戴肺功能监测与 COPD 闭环筛查系统研究**

在线访问：<https://pulmomask.github.io/>

---

## 网站简介

本网站面向项目公开展示，聚焦以下内容：

- 项目背景与研究目标
- 系统构成与闭环流程（监测—评估—反馈）
- 阶段性进展与原型状态
- 团队与合作支持信息
- 联系方式与二维码入口

网站仅展示非保密信息；涉及未公开论文、专利申请及可实施技术细节的内容暂不公开。

---

## 栏目结构

- `Home`：项目总览、系统特色与公开说明
- `Progress`：时间线与阶段状态
- `Team`：项目成员、指导教师与合作支持
- `Contact`：对外联系与项目二维码

---

## 本地预览

推荐使用 Docker（避免污染全局环境）：

```bash
docker compose pull
docker compose up
```

打开：<http://localhost:8080>

停止：

```bash
docker compose down
```

详细说明见：`DEPLOY_ZH.md`

---

## 部署说明

本仓库为 GitHub 用户主页仓库：`pulmomask.github.io`。

- 推送到 `main` 后触发 GitHub Actions 构建
- 构建产物发布到 `gh-pages` 分支
- GitHub Pages 对外地址：<https://pulmomask.github.io/>

若首次部署出现 404，请在仓库设置中确认 Pages 来源为 `gh-pages` 分支 `/ (root)`。

---

## 致谢

本网站基于开源项目 **al-folio** 进行定制开发。

- 项目地址：<https://github.com/alshedivat/al-folio>

感谢 `al-folio` 团队与社区提供优秀的 Jekyll 学术主页模板与持续维护支持。
