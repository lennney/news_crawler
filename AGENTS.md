# Agent — 每日新闻聚合器

一句话：多源新闻爬虫 + 前端卡片展示，个人每日新闻阅读工具。

## 命令

```bash
# 爬虫（待实现）
cd news && python crawler.py

# 前端开发（待搭建）
cd news && npx serve .
```

## 技术栈

- 爬虫：Python 3.12（httpx + BeautifulSoup / playwright）
- 前端：纯 HTML/CSS/JS（卡片式布局，无框架）
- 数据：JSON 文件存储（`news/data/`），暂不需要数据库

## 数据模型

```json
{
  "id": "sha256(url)",
  "title": "",
  "url": "",
  "source": "",
  "summary": "",
  "published_at": "ISO8601",
  "cover_image": "https://...",
  "crawled_at": "ISO8601"
}
```

分类/tags 先跳过，跑一阵子有数据了再加。

## 约束（按优先级）

1. 爬虫要有 User-Agent 和 delay，尊重 robots.txt
2. 数据存 JSON，每次爬取增量追加
3. 前端卡片响应式 3 列 → 2 列 → 1 列

## 边界

- ✅ **Always:** 更新 HANDOVER.md、去重用 url hash
- ⚠️ **Ask:** 换爬虫框架、加数据库、加新数据源
- 🚫 **Never:** 跳过机器人协议、硬编码密钥

## 陷阱（症状 → 原因 → 解决）

- （暂无，爬虫开始跑了再追加）

## 按需文档

- 架构: `docs/architecture.md`
- 爬虫策略: `docs/crawler-strategy.md`
- 决策: `docs/decisions/`
- 踩坑: `LEARNINGS.md`
