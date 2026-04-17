---
name: aipioneer-style-v2
description: |
  AI Pioneer 公众号排版样式 v2.0 - 高级极简风格
  新增：渐变深度、首字下沉、数据高亮、引用升级、品牌签名、阅读进度
---

# AI Pioneer 样式 v2.0

## 版本信息

- **版本**: v2.0.0
- **名称**: AI Pioneer 高级极简
- **状态**: 开发中
- **基于**: v1.0 纯黑样式
- **升级日期**: 2026-04-17

## v2 核心升级

### 1. 视觉深度

| v1 | v2 |
|----|-----|
| 纯平黑色 | 渐变 + 微阴影 |
| 固定章节数字 | 渐变透明数字 |
| 单色强调 | 下划线/背景高亮 |

**渐变系统**:
```css
主渐变: linear-gradient(135deg, #000 0%, #333 100%)
背景渐变: linear-gradient(135deg, rgba(0,0,0,0.03) 0%, rgba(0,0,0,0.08) 100%)
章节数字: linear-gradient(135deg, rgba(0,0,0,0.08) 0%, rgba(0,0,0,0.03) 100%)
```

### 2. 首字下沉 (Drop Cap)

```html
<span style="float:left;font-size:64px;font-weight:700;color:#000;line-height:0.8;margin-right:8px;margin-top:4px;">一</span>
```

效果：段落首字 4 倍大，黑色粗体，营造杂志感。

### 3. 数据高亮块

```html
<div style="margin:24px 0;padding:20px;background:linear-gradient(135deg, rgba(0,0,0,0.03) 0%, rgba(0,0,0,0.08) 100%);border-radius:12px;border-left:4px solid #000;">
  <p style="margin:0 0 8px;font-size:12px;color:#666;text-transform:uppercase;letter-spacing:1px;">关键数据</p>
  <p style="margin:0;font-size:32px;font-weight:700;color:#000;line-height:1.2;">$500M+</p>
  <p style="margin:4px 0 0;font-size:14px;color:#333;">描述文字</p>
</div>
```

### 4. 引用块升级

```html
<blockquote style="margin:24px 0;padding:20px 24px;background:#fafafa;border-left:4px solid #000;border-radius:0 8px 8px 0;position:relative;">
  <span style="position:absolute;top:12px;left:16px;font-size:48px;color:rgba(0,0,0,0.1);line-height:1;">"</span>
  <p style="margin:0 0 12px;font-size:16px;color:#333;line-height:1.8;font-style:italic;padding-left:20px;">
    引用内容
  </p>
  <p style="margin:0;padding-left:20px;font-size:14px;color:#666;">
    —— <b style="color:#000;">作者</b> 职位
  </p>
</blockquote>
```

### 5. 阅读进度条

```html
<div style="position:fixed;top:0;left:0;width:100%;height:3px;background:rgba(0,0,0,0.1);z-index:100;">
  <div style="width:0%;height:100%;background:linear-gradient(90deg, #000 0%, #333 100%);transition:width 0.3s;" id="progress-bar"></div>
</div>

<script>
window.addEventListener('scroll', function() {
  var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
  var scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
  var progress = (scrollTop / scrollHeight) * 100;
  document.getElementById('progress-bar').style.width = progress + '%';
});
</script>
```

### 6. 品牌签名档

```html
<div style="margin:24px 0;padding:20px;background:#fafafa;border-radius:12px;display:flex;align-items:center;gap:16px;">
  <div style="width:56px;height:56px;background:linear-gradient(135deg, #000 0%, #333 100%);border-radius:50%;display:flex;align-items:center;justify-content:center;color:#fff;font-size:24px;font-weight:700;">A</div>
  <div>
    <p style="margin:0 0 4px;font-size:16px;font-weight:700;color:#000;">AI Pioneer</p>
    <p style="margin:0;font-size:13px;color:#666;">探索 AI 时代的机遇与洞察</p>
    <p style="margin:8px 0 0;font-size:12px;color:#999;">
      <span style="margin-right:12px;">🐦 @AI_Pioneer</span>
      <span>📧 contact@aipioneer.com</span>
    </p>
  </div>
</div>
```

## 完整组件库

### 顶部品牌区

```html
<p style="margin:0 0 20px;padding:20px 0;border-bottom:1px solid rgba(0,0,0,0.1);">
  <span style="display:inline-flex;align-items:center;gap:10px;">
    <span style="width:40px;height:40px;background:linear-gradient(135deg, #000 0%, #333 100%);border-radius:8px;display:inline-flex;align-items:center;justify-content:center;color:#fff;font-size:20px;font-weight:700;">A</span>
    <span style="font-size:16px;font-weight:700;color:#000;">AI Pioneer</span>
  </span>
  <span style="float:right;font-size:12px;color:#666;padding-top:12px;">深度观点 · 5分钟阅读</span>
</p>
```

### 数据对比卡片

```html
<div style="margin:24px 0;display:flex;gap:16px;flex-wrap:wrap;">
  <div style="flex:1;min-width:140px;padding:16px;background:linear-gradient(135deg, #000 0%, #222 100%);border-radius:12px;color:#fff;">
    <p style="margin:0 0 4px;font-size:12px;opacity:0.8;">标题</p>
    <p style="margin:0;font-size:28px;font-weight:700;">数值</p>
    <p style="margin:4px 0 0;font-size:12px;opacity:0.8;">描述</p>
  </div>
  <div style="flex:1;min-width:140px;padding:16px;background:#f0f0f0;border-radius:12px;">
    <p style="margin:0 0 4px;font-size:12px;color:#666;">标题</p>
    <p style="margin:0;font-size:28px;font-weight:700;color:#999;">数值</p>
    <p style="margin:4px 0 0;font-size:12px;color:#666;">描述</p>
  </div>
</div>
```

### 图片卡片

```html
<div style="margin:24px 0;border-radius:12px;overflow:hidden;box-shadow:0 4px 20px rgba(0,0,0,0.1);">
  <img src="图片URL" style="width:100%;display:block;" alt="描述">
  <div style="padding:12px 16px;background:#f8f8f8;">
    <p style="margin:0;font-size:13px;color:#666;">📷 图片说明</p>
  </div>
</div>
```

### 分隔线

```html
<div style="margin:32px 0;text-align:center;">
  <span style="display:inline-block;width:8px;height:8px;background:#000;border-radius:50%;margin:0 8px;"></span>
  <span style="display:inline-block;width:8px;height:8px;background:rgba(0,0,0,0.3);border-radius:50%;margin:0 8px;"></span>
  <span style="display:inline-block;width:8px;height:8px;background:rgba(0,0,0,0.1);border-radius:50%;margin:0 8px;"></span>
</div>
```

## 与 v1 对比

| 特性 | v1 | v2 |
|------|-----|-----|
| 视觉深度 | 纯平 | 渐变 + 阴影 |
| 首字下沉 | ❌ | ✅ |
| 数据高亮 | 简单引用 | 独立卡片 |
| 引用样式 | 背景块 | 左边框 + 引号 |
| 阅读进度 | ❌ | ✅ |
| 品牌签名 | ❌ | ✅ |
| 作者信息 | ❌ | 头像 + 简介 |
| 二维码区 | ❌ | ✅ |
| 底部导航 | ❌ | ✅ |

## 使用方式

```bash
# 使用 v2 样式
npx aipioneer-publisher publish "链接" --theme ai-pioneer-v2
```

## 版本历史

| 版本 | 日期 | 变更 |
|------|------|------|
| v1.0 | 2026-04-17 | 初始版本，纯黑极简 |
| v2.0 | 2026-04-17 | 高级极简，增加深度和交互 |
