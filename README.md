# liNterNoka_11

个人归档站。Hugo + PaperMod 静态生成，部署在 GitHub Pages。

线上：<https://linternoka.github.io/>

## 结构

```
hugo.toml                    站点配置（导航、taxonomy、首页 profile）
content/
  _index.md                  首页正文
  archive/                   归档条目，一条一个 md
  works/                     推荐作品
  archives.md                归档页（layout: archives）
  search.md                  搜索页
  about.md                   关于
data/subjects.yaml           首页三张分科卡片的标题、分类与链接
layouts/_shortcodes/subject-cards.html  首页分科卡片
assets/css/extended/kam.css  唯一的样式覆盖，只改排版与配色
themes/PaperMod              submodule，锁在 1181196
.github/workflows/hugo.yml   构建与部署
```

## 首页

正文写在 `content/_index.md`。三张分科卡片由 `{{< subject-cards >}}` 插在正文中间，
卡片内容在 `data/subjects.yaml`：`term` 用来统计该分类的条目数，`href` 指向点进去的分类页。

## 加一条归档

在 `content/archive/` 放一个 md：

```yaml
---
title: "萌百：条目「XXX」整段重写"
date: 2026-05-12
platform: ["moegirl"]      # 决定 /platforms/moegirl/ 分面页
kind: ["edit"]             # 决定 /kinds/edit/ 分面页
summary: "一句话说清改了什么。"
---
```

正文写一句说明加外链。`url` 字段改的是页面地址，别用来存外链，用 `source`。

## 本地预览

```powershell
hugo server -D
```

打开 http://127.0.0.1:1313/ 。Hugo 0.170 已装在 winget 里。

## 主题版本

PaperMod 的 v8.0 在 Hugo 0.170 下会报 `site.Social` 不存在（Hugo 删了这个字段），
master 已迁到新的 `layouts/_partials/` 结构，所以锁在 master 的提交 `1181196`。
升级主题时先在本机跑一次 `hugo --minify`，过了再改 submodule。

## 部署

推送 `main` → GitHub Actions 跑 `hugo --minify --gc` → 部署 Pages。
本机 git 全局代理指向没启动的 7897，推送要绕开：`git -c http.proxy= -c https.proxy= push`。
构建产物约 0.8 MB。Pages 的 Source 必须是「GitHub Actions」，不是分支。

## 待办

- 私有档案仓（快照 + sha256 校验）还没建，目前归档条目是手写的。
- 老站 `Linternoka/personal-blog`（Next.js）已下线归档。