# 个人网页设计风格文档

## 概述

本文档描述张银豪个人作品集网页的设计风格系统，涵盖色彩、字体、布局、动效等各个方面。

---

## 色彩系统

### 主色调

| 变量名 | 色值 | 用途 |
|--------|------|------|
| `--primary` | `#FF6B35` | 主色，橙色，用于CTA按钮、主要强调 |
| `--primary-light` | `#FF8C5A` | 主色浅调，用于hover状态 |
| `--secondary` | `#4ECDC4` | 辅色，青绿色，用于标签、次要元素 |
| `--accent` | `#FFE66D` | 强调色，黄色，用于装饰、高亮 |

### 中性色

| 变量名 | 色值（浅色模式）| 用途 |
|--------|-----------------|------|
| `--dark` | `#2D3436` | 深色，用于边框、标题 |
| `--light` | `#FAFAFA` | 浅色，浅色背景 |
| `--gray` | `#636E72` | 灰色，辅助文字 |
| `--card-bg` | `#FFFFFF` | 卡片背景 |
| `--text-primary` | `#2D3436` | 主要文字 |
| `--text-secondary` | `#636E72` | 次要文字 |
| `--bg-primary` | `#FAFAFA` | 主背景 |
| `--bg-secondary` | `#FFFFFF` | 次背景 |
| `--border-color` | `#2D3436` | 边框色 |

### 暗色模式变量

```css
--primary: #FF8C5A;
--primary-light: #FFAB7A;
--secondary: #6ED9D0;
--dark: #FAFAFA;
--light: #1A1A2E;
--card-bg: #16213E;
--text-primary: #FAFAFA;
--text-secondary: #A0A0A0;
--bg-primary: #0F0F1A;
--bg-secondary: #1A1A2E;
--border-color: #3A3A5A;
```

---

## 字体系统

### 字体栈

- **标题字体**: `'Space Grotesk', sans-serif`
- **正文字体**: `'Noto Sans SC', 'Space Grotesk', sans-serif`
- **Fallback**: `system-ui, sans-serif`

### 字体使用规范

| 元素 | 字体 | 字号 | 字重 |
|------|------|------|------|
| Hero标题 | Space Grotesk | clamp(48px, 8vw, 96px) | 900 |
| 章节标题 | Space Grotesk | clamp(36px, 5vw, 56px) | 900 |
| 卡片标题 | Noto Sans SC | 20-28px | 700 |
| 正文 | Noto Sans SC | 14-16px | 400-500 |
| 标签文字 | Noto Sans SC | 11-13px | 600 |
| 统计数据 | Space Grotesk | 48px | 700 |

### 文字间距

- 标题 letter-spacing: -1px 到 -2px
- 正文 line-height: 1.6
- 标题 line-height: 1.1 到 1.3

---

## 间距系统

使用8px基准的间距系统：

| 变量名 | 值 | 用途 |
|--------|-----|------|
| `--spacing-xs` | 8px | 紧凑间距 |
| `--spacing-sm` | 16px | 小间距 |
| `--spacing-md` | 24px | 中等间距 |
| `--spacing-lg` | 40px | 大间距 |
| `--spacing-xl` | 60px | 特大间距 |
| `--spacing-2xl` | 120px | 超大间距（section padding） |

---

## 圆角系统

| 变量名 | 值 | 用途 |
|--------|-----|------|
| `--radius-sm` | 8px | 按钮、输入框 |
| `--radius-md` | 15px | 小卡片 |
| `--radius-lg` | 20px | 大卡片、容器 |
| `--radius-xl` | 30px | 特殊元素 |

---

## 过渡动画

| 变量名 | 值 | 用途 |
|--------|-----|------|
| `--transition-fast` | 0.15s | 微交互 |
| `--transition-normal` | 0.3s | 标准过渡 |
| `--transition-slow` | 0.5s | 大型动画 |

---

## 布局结构

### 页面最大宽度

- 容器: `1400px`
- 内边距: `40px`（桌面）/ `20px`（移动）

### 栅格系统

| 组件 | 列数 | 间距 |
|------|------|------|
| 项目卡片网格 | 3列 | 30px |
| 文章网格 | 3列 | 30px |
| 技能卡片 | 3列 | 40px |
| AI实践卡片 | 4列 | 30px |
| 经验卡片 | 2列 | 30px |
| 教育卡片 | 3列 | 30px |

### 响应式断点

- **1024px**: 平板，技能/教育卡片变为1列
- **768px**: 大手机，调整导航和hero布局
- **480px**: 小手机，进一步简化布局

---

## 组件样式

### 卡片组件

**项目卡片**
```css
background: var(--card-bg);
border: 3px solid var(--border-color);
border-radius: 20px;
padding: 25px;
transition: all 0.3s;
```

**卡片悬停效果**
```css
transform: translate(-5px, -5px);
box-shadow: 10px 10px 0 var(--border-color);
```

**深色卡片（用于articles、AI实践section）**
```css
background: rgba(255, 255, 255, 0.05);
border: 2px solid rgba(255, 255, 255, 0.1);
border-radius: 20px;
```

### 按钮组件

**主要按钮**
```css
background: var(--text-primary);
color: var(--bg-primary);
padding: 16px 32px;
border-radius: 8px;
font-weight: 600;
```

**次要按钮**
```css
background: transparent;
border: 2px solid var(--border-color);
padding: 14px 30px;
border-radius: 8px;
```

### 标签组件

**项目标签**
```css
background: var(--primary);
color: white;
padding: 4px 10px;
border-radius: 20px;
font-size: 11px;
font-weight: 600;
text-transform: uppercase;
letter-spacing: 0.5px;
```

### 章节标题

```css
.section-title {
    font-size: clamp(36px, 5vw, 56px);
    font-weight: 900;
    letter-spacing: -1px;
}

.section-title .number {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 0.5em;
    color: var(--primary);
    vertical-align: super;
    margin-right: 10px;
}
```

---

## 导航栏

```css
position: fixed;
top: 0;
background: var(--bg-secondary);
backdrop-filter: blur(10px);
border-bottom: 3px solid var(--border-color);
```

导航链接下划线动画：
```css
.nav-links a::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 3px;
    background: var(--primary);
    transition: width var(--transition-normal);
}

.nav-links a:hover::after,
.nav-links a.active::after {
    width: 100%;
}
```

---

## Hero区域

### 统计数据展示

```css
.stat-number {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 48px;
    font-weight: 700;
    line-height: 1;
}

.stat-number .unit {
    font-size: 24px;
    color: var(--primary);
}
```

### 浮动徽章

```css
.floating-badge {
    position: absolute;
    background: var(--bg-secondary);
    border: 3px solid var(--border-color);
    border-radius: 15px;
    padding: 12px 15px;
    box-shadow: 8px 8px 0 var(--border-color);
}

@keyframes float {
    0%, 100% { transform: translateY(0) rotate(0deg); }
    50% { transform: translateY(-10px) rotate(2deg); }
}
```

---

## 阴影效果

### 卡片悬停阴影

```css
box-shadow: 10px 10px 0 var(--border-color);
transform: translate(-5px, -5px);
```

### 常规阴影

```css
box-shadow: 0 4px 20px rgba(0,0,0,0.08);
```

---

## 装饰元素

### 背景网格

```css
.decoration-grid {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    pointer-events: none;
    z-index: -1;
    opacity: 0.03;
    background-image:
        linear-gradient(var(--text-primary) 1px, transparent 1px),
        linear-gradient(90deg, var(--text-primary) 1px, transparent 1px);
    background-size: 60px 60px;
}
```

### 径向渐变背景

Hero区域使用径向渐变创建光晕效果：
```css
.hero::before {
    top: -50%;
    right: -20%;
    width: 800px;
    height: 800px;
    background: radial-gradient(circle, rgba(78, 205, 196, 0.15) 0%, transparent 70%);
}
```

---

## 无障碍设计

### 焦点样式

```css
:focus-visible {
    outline: 3px solid var(--primary);
    outline-offset: 2px;
}
```

### 减少动画

```css
@media (prefers-reduced-motion: reduce) {
    html { scroll-behavior: auto; }
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}
```

### 屏幕阅读器辅助

```css
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
}
```

---

## 技能条

```css
.skill-bar {
    height: 8px;
    background: var(--bg-primary);
    border-radius: 4px;
    overflow: hidden;
}

.skill-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--primary), var(--secondary));
    border-radius: 4px;
    transition: width 1s ease-out;
}
```

---

## 时间线

```css
.timeline-marker {
    width: 16px;
    height: 16px;
    background: var(--primary);
    border-radius: 50%;
}

.timeline-marker::after {
    content: '';
    position: absolute;
    top: 20px;
    left: 50%;
    transform: translateX(-50%);
    width: 2px;
    height: calc(100% - 20px);
    background: var(--border-color);
}
```

---

## 设计特点总结

1. **活力配色**: 橙色+青绿色+黄色，传递技术派+创新+趣味的个性
2. **卡片式布局**: 清晰的模块化信息组织
3. **强调边框**: 使用深色边框而非阴影，保持清晰的边界感
4. **微动效**: hover时的位移+阴影变化，增加交互反馈
5. **大号数字**: 项目编号、统计数据使用Space Grotesk大号字体
6. **段落编号**: 章节使用小号彩色数字作为装饰
7. **浮动元素**: 头像旁的浮动徽章，增添趣味性
8. **径向光晕**: Hero区域使用半透明渐变作为装饰

---

*本文档基于 index.html v1.0 生成*
