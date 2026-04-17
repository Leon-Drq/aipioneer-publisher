---
name: aipioneer-style-v2
description: |
  AI Pioneer 公众号排版样式 v2.0 - 简洁版
  在 v1.0 基础上添加品牌头图，其他保持简洁
---

# AI Pioneer 样式 v2.0（简洁版）

## 版本信息

- **版本**: v2.0.0
- **名称**: AI Pioneer + 品牌头图
- **基于**: v1.0 纯黑样式
- **变更**: 顶部添加品牌头图

## 与 v1 的区别

```
v1: [标签] → [内容]
v2: [品牌头图] → [标签] → [内容]
```

## 品牌头图

```html
<p style="margin:0 0 20px;text-align:center;">
  <img src="ai-pioneer-header.png" style="max-width:100%;height:auto;" alt="AI PIONEER">
</p>
```

**要求**:
- 图片宽度：900px（微信推荐）
- 高度：建议 100-150px
- 背景：白色或透明
- 文字：AI PIONEER（大写）

## 完整结构

```html
<!-- 1. 品牌头图（新增） -->
<p style="margin:0 0 20px;text-align:center;">
  <img src="header.png" style="max-width:100%;height:auto;" alt="AI PIONEER">
</p>

<!-- 2. 标签（v1 原有） -->
<p style="margin:0 0 10px;">
  <span style="display:inline-block;background:#000000;color:#ffffff;font-size:11px;padding:3px 12px;border-radius:20px;letter-spacing:1.5px;">AI Pioneer · 深度观点</span>
</p>

<!-- 3. 内容（v1 原有） -->
...

<!-- 4. 结尾（v1 原有） -->
...
```

## 使用方式

```bash
npx aipioneer-publisher publish "链接" --theme ai-pioneer-v2
```

## 版本对比

| 版本 | 特点 | 适用场景 |
|------|------|----------|
| v1.0 | 极简，无头图 | 快速阅读，内容优先 |
| v2.0 | 简洁 + 品牌头图 | 品牌强化，系列文章 |
