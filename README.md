# 系统安全 & 功能安全 · 学习笔记

个人学习提纲，面向求职（自动驾驶 / 嵌入式系统安全方向），按主题分页面沉淀，并穿插深度学习相关内容。
纯静态站点，零构建步骤，可直接托管在 GitHub Pages。

## 目录结构

```
security-notes/
├── index.html                # 首页：主题导航 + 使用说明
├── functional-safety.html    # 功能安全（ISO 26262 / SOTIF / DL 在安全关键系统）
├── system-security.html      # 系统安全·信息安全（ISO 21434 / TARA / 对抗样本）
├── assets/
│   └── style.css             # 共享样式（克制单色系，反"AI 土味"）
└── .nojekyll                 # 关闭 GitHub Pages 的 Jekyll 处理
```

## 本地预览

直接用浏览器打开 `index.html` 即可；或起一个本地服务（路径更贴近线上）：

```bash
# 在 security-notes/ 目录下
python -m http.server 8000
# 浏览器访问 http://localhost:8000
```

## 部署到 GitHub Pages（推到你自己账号）

1. 在 GitHub 新建一个仓库，例如 `security-notes`（建议仓库名全小写、无中文）。
2. 把 `security-notes/` 整个目录的内容推上去：

```bash
cd security-notes
git init
git add .
git commit -m "init: 系统安全与功能安全学习笔记"
git branch -M main
git remote add origin git@github.com:<你的用户名>/security-notes.git
git push -u origin main
```

3. 仓库 → **Settings → Pages** → Source 选择 **main** 分支、目录 **/ (root)** → Save。
4. 几分钟后访问 `https://<你的用户名>.github.io/security-notes/`。

> 如果用 HTTPS 而非 SSH，把 `git remote add` 的地址换成 `https://github.com/<你的用户名>/security-notes.git`。

## 如何新增一个页面

1. 复制 `functional-safety.html` 重命名为 `xxx.html`，改 `<title>`、导航 `active`、`<h1>` 与内容。
2. 在 `index.html` 的 `.cards` 区块加一张卡片链接过去。
3. 在另外两个页面的导航 `<nav class="top">` 里补上链接（保持三页导航一致）。
4. 提交推送即可，GitHub Pages 会自动更新。

## 设计说明

样式刻意采用克制单色系、无渐变发光、统一间距与真实排版（参照 unslop 反"AI 土味"原则），
确保在简历/面试前作为可展示的个人学习站也显得干净、专业。

## 内容来源

- ISO 26262（道路车辆功能安全）、ISO 21448（SOTIF，预期功能安全）、ISO/SAE 21434（道路车辆网络安全工程）等公开标准摘要
- 个人项目经验（激光雷达脏污检测、知识图谱、3D 重建等）与安全工程的关联整理
- 早期功能安全实习面试速成材料的重构与扩展
