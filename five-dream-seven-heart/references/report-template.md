# 报告模板与设计原则（Impeccable风格）

## 目录
- 一、设计原则
- 二、配色方案
- 三、字体规范
- 四、间距系统
- 五、HTML报告模板（深度模式完整版）
- 六、HTML报告模板（快速模式精简版）
- 七、分享卡片模板
- 八、报告内容撰写规范
- 九、吉凶参考撰写规范
- 十、报告禁止事项
- 十一、报告推荐语气

## 一、设计原则

### 1. 视觉层级
- 清晰的字号层级（标题 > 副标题 > 正文 > 辅助）
- 合理的留白和间距
- 不用过度装饰

### 2. 配色方案
- 符合梦境主题：神秘、温暖、有深度
- 使用靛蓝瓷配色（Indigo Porcelain）
- 拒绝纯黑纯白，使用tint色彩

### 3. 排版规范
- 正文行高适中，确保可读性
- 卡片式布局区分不同"心相"
- 避免纯文字堆砌

### 4. 报告模式
- 深度模式：完整七心相报告
- 快速模式：三心相精简报告（欲望之镜+意象之林+行动之引）

## 二、配色方案

```css
/* 梦境主题 - 靛蓝瓷配色 */
:root {
  /* 主色调 */
  --ink: #2d3748;           /* 深墨色 - 主文字 */
  --ink-secondary: #718096;  /* 灰墨色 - 次要文字 */
  --ink-muted: #a0aec0;     /* 淡墨色 - 辅助文字 */

  /* 背景色 */
  --paper: #faf9f7;         /* 暖白 - 主背景 */
  --paper-secondary: #f0efed; /* 米灰 - 次要背景 */
  --paper-card: #ffffff;    /* 纯白 - 卡片背景 */

  /* 强调色 */
  --accent: #6b5b95;        /* 神秘紫 - 主强调 */
  --accent-warm: #b4846c;   /* 暖棕 - 辅助强调 */
  --accent-cool: #5a7d8c;   /* 静蓝 - 信息强调 */

  /* 语义色 */
  --positive: #68a67d;      /* 平和绿 - 积极/成长 */
  --warning: #c9956c;       /* 焦糖橙 - 提醒/关注 */
  --mystery: #8b7aa7;       /* 神秘紫 - 玄学视角 */

  /* 边框与分隔 */
  --border: #e2e0dd;         /* 暖灰边框 */
  --divider: #f0efed;       /* 分隔线 */

  /* 阴影 */
  --shadow-sm: 0 1px 2px rgba(45, 55, 72, 0.05);
  --shadow-md: 0 4px 12px rgba(45, 55, 72, 0.08);
}
```

## 三、字体规范

```css
:root {
  /* 中文优先 */
  --font-heading: 'Noto Serif SC', 'Source Han Serif CN', Georgia, serif;
  --font-body: 'Noto Sans SC', 'PingFang SC', 'Microsoft YaHei', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;

  /* 字阶 */
  --text-xs: 0.75rem;     /* 12px - 注释 */
  --text-sm: 0.875rem;    /* 14px - 辅助 */
  --text-base: 1rem;       /* 16px - 正文 */
  --text-lg: 1.125rem;    /* 18px - 大正文 */
  --text-xl: 1.25rem;     /* 20px - 副标题 */
  --text-2xl: 1.5rem;     /* 24px - 标题 */
  --text-3xl: 1.875rem;   /* 30px - 大标题 */
}
```

## 四、间距系统

```css
:root {
  --space-1: 0.25rem;   /* 4px */
  --space-2: 0.5rem;    /* 8px */
  --space-3: 0.75rem;   /* 12px */
  --space-4: 1rem;       /* 16px */
  --space-5: 1.25rem;   /* 20px */
  --space-6: 1.5rem;    /* 24px */
  --space-8: 2rem;       /* 32px */
  --space-10: 2.5rem;    /* 40px */
  --space-12: 3rem;      /* 48px */
  --space-16: 4rem;      /* 64px */
}
```

## 五、HTML报告模板（深度模式完整版）

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>「五梦七心相」心相分析报告</title>
  <style>
    /* 基础重置 */
    * { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --ink: #2d3748;
      --ink-secondary: #718096;
      --ink-muted: #a0aec0;
      --paper: #faf9f7;
      --paper-secondary: #f0efed;
      --paper-card: #ffffff;
      --accent: #6b5b95;
      --accent-warm: #b4846c;
      --accent-cool: #5a7d8c;
      --positive: #68a67d;
      --warning: #c9956c;
      --mystery: #8b7aa7;
      --border: #e2e0dd;

      --font-heading: 'Noto Serif SC', Georgia, serif;
      --font-body: 'Noto Sans SC', sans-serif;

      --text-xs: 0.75rem;
      --text-sm: 0.875rem;
      --text-base: 1rem;
      --text-lg: 1.125rem;
      --text-xl: 1.25rem;
      --text-2xl: 1.5rem;
      --text-3xl: 1.875rem;

      --space-2: 0.5rem;
      --space-3: 0.75rem;
      --space-4: 1rem;
      --space-6: 1.5rem;
      --space-8: 2rem;
      --space-12: 3rem;
      --space-16: 4rem;
    }

    body {
      font-family: var(--font-body);
      background: var(--paper);
      color: var(--ink);
      line-height: 1.7;
      font-size: var(--text-base);
    }

    /* 容器 */
    .container {
      max-width: 720px;
      margin: 0 auto;
      padding: var(--space-8) var(--space-6);
    }

    /* 标题区 */
    .header {
      text-align: center;
      margin-bottom: var(--space-12);
      padding-bottom: var(--space-8);
      border-bottom: 1px solid var(--border);
    }

    .header-badge {
      display: inline-block;
      font-size: var(--text-xs);
      color: var(--accent);
      background: rgba(107, 91, 149, 0.1);
      padding: var(--space-1) var(--space-3);
      border-radius: 100px;
      margin-bottom: var(--space-4);
    }

    .header h1 {
      font-family: var(--font-heading);
      font-size: var(--text-3xl);
      font-weight: 600;
      color: var(--ink);
      margin-bottom: var(--space-3);
    }

    .header-subtitle {
      color: var(--ink-secondary);
      font-size: var(--text-sm);
    }

    /* 梦型标签 */
    .dream-tags {
      display: flex;
      gap: var(--space-2);
      justify-content: center;
      flex-wrap: wrap;
      margin-top: var(--space-4);
    }

    .dream-tag {
      font-size: var(--text-xs);
      padding: var(--space-1) var(--space-3);
      border-radius: 4px;
      background: var(--paper-secondary);
      color: var(--ink-secondary);
    }

    /* 心相卡片 */
    .heart-mirror {
      margin-bottom: var(--space-8);
    }

    .heart-mirror-card {
      background: var(--paper-card);
      border-radius: 12px;
      padding: var(--space-6);
      margin-bottom: var(--space-4);
      box-shadow: 0 1px 2px rgba(45, 55, 72, 0.05);
      border: 1px solid var(--border);
    }

    .heart-mirror-header {
      display: flex;
      align-items: baseline;
      gap: var(--space-3);
      margin-bottom: var(--space-4);
    }

    .heart-mirror-number {
      font-size: var(--text-xs);
      font-weight: 600;
      color: var(--accent);
      background: rgba(107, 91, 149, 0.1);
      padding: 2px 8px;
      border-radius: 4px;
    }

    .heart-mirror-title {
      font-family: var(--font-heading);
      font-size: var(--text-lg);
      font-weight: 600;
      color: var(--ink);
    }

    .heart-mirror-label {
      font-size: var(--text-xs);
      color: var(--ink-muted);
      margin-left: auto;
    }

    .heart-mirror-content {
      color: var(--ink-secondary);
      font-size: var(--text-base);
      line-height: 1.8;
    }

    .heart-mirror-content strong {
      color: var(--ink);
      font-weight: 500;
    }

    .heart-mirror-content p {
      margin-bottom: var(--space-3);
    }

    .heart-mirror-content p:last-child {
      margin-bottom: 0;
    }

    /* 双视角分隔 */
    .view-divider {
      display: flex;
      align-items: center;
      gap: var(--space-3);
      margin: var(--space-6) 0;
    }

    .view-divider::before,
    .view-divider::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    .view-divider span {
      font-size: var(--text-xs);
      color: var(--ink-muted);
      white-space: nowrap;
    }

    /* 吉凶参考区块 */
    .fortune-reference {
      background: linear-gradient(135deg, rgba(139, 122, 167, 0.08), rgba(180, 132, 108, 0.08));
      border-radius: 12px;
      padding: var(--space-6);
      margin-bottom: var(--space-8);
      border: 1px solid rgba(139, 122, 167, 0.15);
    }

    .fortune-reference-title {
      font-family: var(--font-heading);
      font-size: var(--text-lg);
      font-weight: 600;
      color: var(--mystery);
      margin-bottom: var(--space-4);
    }

    .fortune-reference-content {
      color: var(--ink-secondary);
      font-size: var(--text-sm);
      line-height: 1.8;
    }

    .fortune-reference-content .fortune-good {
      color: var(--positive);
      font-weight: 500;
    }

    .fortune-reference-content .fortune-caution {
      color: var(--warning);
      font-weight: 500;
    }

    .fortune-reference-note {
      margin-top: var(--space-3);
      font-size: var(--text-xs);
      color: var(--ink-muted);
      font-style: italic;
    }

    /* 综合心语 */
    .closing-wisdom {
      background: linear-gradient(135deg, rgba(107, 91, 149, 0.05), rgba(180, 132, 108, 0.05));
      border-radius: 12px;
      padding: var(--space-8);
      margin-top: var(--space-12);
      text-align: center;
    }

    .closing-wisdom-title {
      font-family: var(--font-heading);
      font-size: var(--text-xl);
      font-weight: 600;
      color: var(--ink);
      margin-bottom: var(--space-4);
    }

    .closing-wisdom-text {
      font-size: var(--text-lg);
      color: var(--ink-secondary);
      line-height: 1.9;
      font-style: italic;
    }

    /* 梦境日记建议 */
    .dream-diary {
      background: var(--paper-secondary);
      border-radius: 8px;
      padding: var(--space-6);
      margin-top: var(--space-8);
    }

    .dream-diary-title {
      font-family: var(--font-heading);
      font-size: var(--text-lg);
      font-weight: 600;
      color: var(--ink);
      margin-bottom: var(--space-3);
    }

    .dream-diary-content {
      color: var(--ink-secondary);
      font-size: var(--text-sm);
      line-height: 1.8;
    }

    .dream-diary-content ol {
      padding-left: var(--space-6);
      margin-bottom: var(--space-3);
    }

    .dream-diary-content li {
      margin-bottom: var(--space-2);
    }

    /* 分享引导 */
    .share-guide {
      text-align: center;
      margin-top: var(--space-6);
      padding-top: var(--space-4);
      border-top: 1px solid var(--border);
    }

    .share-guide-text {
      font-size: var(--text-xs);
      color: var(--ink-muted);
    }

    /* 用户反馈区域 */
    .feedback-section {
      background: var(--paper-card);
      border-radius: 12px;
      padding: var(--space-6);
      margin-top: var(--space-8);
      border: 1px dashed var(--border);
      text-align: center;
    }

    .feedback-title {
      font-family: var(--font-heading);
      font-size: var(--text-lg);
      font-weight: 600;
      color: var(--ink);
      margin-bottom: var(--space-4);
    }

    .feedback-options {
      display: flex;
      flex-direction: column;
      gap: var(--space-3);
    }

    .feedback-option {
      padding: var(--space-3) var(--space-4);
      border-radius: 8px;
      background: var(--paper-secondary);
      color: var(--ink-secondary);
      font-size: var(--text-sm);
      cursor: pointer;
      transition: background 0.2s;
    }

    .feedback-option:hover {
      background: rgba(107, 91, 149, 0.1);
    }

    /* 五梦归类区块 */
    .dream-classification {
      background: var(--paper-secondary);
      border-radius: 8px;
      padding: var(--space-6);
      margin-bottom: var(--space-8);
    }

    .dream-classification-title {
      font-family: var(--font-heading);
      font-size: var(--text-xl);
      font-weight: 600;
      color: var(--ink);
      margin-bottom: var(--space-4);
    }

    .dream-classification-item {
      margin-bottom: var(--space-3);
    }

    .dream-classification-label {
      font-size: var(--text-xs);
      font-weight: 600;
      color: var(--accent);
      margin-bottom: var(--space-1);
    }

    .dream-classification-content {
      color: var(--ink-secondary);
      font-size: var(--text-sm);
    }

    /* 底部 */
    .footer {
      margin-top: var(--space-12);
      padding-top: var(--space-6);
      border-top: 1px solid var(--border);
      text-align: center;
    }

    .footer-text {
      font-size: var(--text-xs);
      color: var(--ink-muted);
    }

    /* 分享卡片样式 */
    .share-card {
      max-width: 375px;
      margin: var(--space-8) auto;
      background: linear-gradient(135deg, #2d3748, #4a5568);
      border-radius: 16px;
      padding: var(--space-8);
      color: #faf9f7;
      text-align: center;
    }

    .share-card-badge {
      font-size: var(--text-xs);
      color: rgba(250, 249, 247, 0.6);
      background: rgba(250, 249, 247, 0.1);
      padding: var(--space-1) var(--space-3);
      border-radius: 100px;
      display: inline-block;
      margin-bottom: var(--space-4);
    }

    .share-card-dream-type {
      font-size: var(--text-xs);
      color: var(--accent-warm);
      margin-bottom: var(--space-2);
    }

    .share-card-keyword {
      font-family: var(--font-heading);
      font-size: var(--text-2xl);
      font-weight: 600;
      color: #faf9f7;
      margin-bottom: var(--space-4);
    }

    .share-card-message {
      font-size: var(--text-sm);
      color: rgba(250, 249, 247, 0.8);
      line-height: 1.8;
      font-style: italic;
    }

    .share-card-footer {
      margin-top: var(--space-6);
      font-size: var(--text-xs);
      color: rgba(250, 249, 247, 0.4);
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- 标题区 -->
    <header class="header">
      <span class="header-badge">心相分析报告</span>
      <h1>「五梦七心相」</h1>
      <p class="header-subtitle">分析时间：[日期]</p>
      <div class="dream-tags">
        <span class="dream-tag">[梦型标签]</span>
      </div>
    </header>

    <!-- 五梦归类 -->
    <section class="dream-classification">
      <h2 class="dream-classification-title">五梦归类</h2>
      <div class="dream-classification-item">
        <div class="dream-classification-label">梦型判定</div>
        <div class="dream-classification-content">[梦型判定结果及依据]</div>
      </div>
      <div class="dream-classification-item">
        <div class="dream-classification-label">梦日溯源</div>
        <div class="dream-classification-content">
          近期印象：[梦日关键事件]<br>
          躯体刺激：[睡眠身体感觉]
        </div>
      </div>
    </section>

    <!-- 心相一：欲望之镜 -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">一</span>
          <h2 class="heart-mirror-title">欲望之镜</h2>
          <span class="heart-mirror-label">核心动机</span>
        </div>
        <div class="heart-mirror-content">
          <p>[欲望之镜分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 心相二：情感之流 -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">二</span>
          <h2 class="heart-mirror-title">情感之流</h2>
          <span class="heart-mirror-label">情绪线索</span>
        </div>
        <div class="heart-mirror-content">
          <p>[情感之流分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 双视角分隔 -->
    <div class="view-divider">
      <span>心理学 · 传统易学</span>
    </div>

    <!-- 心相三：意象之林（双视角） -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">三</span>
          <h2 class="heart-mirror-title">意象之林</h2>
          <span class="heart-mirror-label">关键象征</span>
        </div>
        <div class="heart-mirror-content">
          <p><strong>心理学视角</strong></p>
          <p>[心理学意象解读]</p>
          <p><br></p>
          <p><strong>传统易学视角</strong></p>
          <p>[传统意象解读]</p>
        </div>
      </div>
    </section>

    <!-- 心相四：关系之网 -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">四</span>
          <h2 class="heart-mirror-title">关系之网</h2>
          <span class="heart-mirror-label">人物映射</span>
        </div>
        <div class="heart-mirror-content">
          <p>[关系之网分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 心相五：冲突之地 -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">五</span>
          <h2 class="heart-mirror-title">冲突之地</h2>
          <span class="heart-mirror-label">未解情结</span>
        </div>
        <div class="heart-mirror-content">
          <p>[冲突之地分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 心相六：天人之机（仅玄学框架） -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">六</span>
          <h2 class="heart-mirror-title">天人之机</h2>
          <span class="heart-mirror-label">传统视角</span>
        </div>
        <div class="heart-mirror-content">
          <p>[天人之机分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 吉凶参考（仅玄学框架） -->
    <section class="fortune-reference">
      <h2 class="fortune-reference-title">☯ 吉凶参考</h2>
      <div class="fortune-reference-content">
        <p><span class="fortune-good">近期宜：</span>[基于卦象和梦型的行动建议]</p>
        <p><span class="fortune-caution">近期忌：</span>[基于卦象和梦型的注意事项]</p>
      </div>
      <p class="fortune-reference-note">* 以上仅为传统解读参考，你的行动和心态才是决定因素。</p>
    </section>

    <!-- 心相七：行动之引 -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">七</span>
          <h2 class="heart-mirror-title">行动之引</h2>
          <span class="heart-mirror-label">实践指引</span>
        </div>
        <div class="heart-mirror-content">
          <p>[行动之引分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 综合心语 -->
    <section class="closing-wisdom">
      <h2 class="closing-wisdom-title">综合心语</h2>
      <p class="closing-wisdom-text">
        [综合心语内容，温暖柔和，50-80字]
      </p>
    </section>

    <!-- 梦境日记建议 -->
    <section class="dream-diary">
      <h2 class="dream-diary-title">🌙 梦境日记建议</h2>
      <div class="dream-diary-content">
        <p>如果你想持续探索自己的梦境世界，可以试试这个方法：</p>
        <ol>
          <li>每天醒来后，花1分钟记录梦境关键词（画面、情绪、人物）</li>
          <li>一周后回顾，看看有没有重复出现的主题或意象</li>
          <li>一个月后再次解读，你会发现自己更深层的心理模式</li>
        </ol>
        <p>梦境是潜意识写给自己的信。坚持记录，你会慢慢读懂它的语言。</p>
      </div>
    </section>

    <!-- 分享引导 -->
    <div class="share-guide">
      <p class="share-guide-text">这份报告属于你。如果想分享给朋友，可以截图保存。你的梦境，你的心相。</p>
    </div>

    <!-- 分享卡片 -->
    <section class="share-card">
      <span class="share-card-badge">五梦七心相</span>
      <p class="share-card-dream-type">[梦型标签]</p>
      <p class="share-card-keyword">「[核心意象词]」</p>
      <p class="share-card-message">[一句话心语，如"这个梦不是警告，而是一份温柔的情书"]</p>
      <p class="share-card-footer">— 五梦七心相 · 心相分析报告</p>
    </section>

    <!-- 用户反馈 -->
    <section class="feedback-section">
      <h2 class="feedback-title">这份解读对你有帮助吗？</h2>
      <div class="feedback-options">
        <div class="feedback-option">💡 很有帮助，让我更了解自己</div>
        <div class="feedback-option">🌱 有一些启发，但还想深入了解</div>
        <div class="feedback-option">💭 和我的感受不太一样，想再聊聊</div>
      </div>
    </section>

    <!-- 底部 -->
    <footer class="footer">
      <p class="footer-text">心相之道，在于观象见心，以梦为镜</p>
    </footer>
  </div>
</body>
</html>
```

## 六、HTML报告模板（快速模式精简版）

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>「五梦七心相」快速心相报告</title>
  <style>
    /* 复用深度模式的完整CSS，此处仅列出差异部分 */

    /* 快速模式标识 */
    .header-badge {
      background: rgba(90, 125, 140, 0.1);
      color: var(--accent-cool);
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- 标题区 -->
    <header class="header">
      <span class="header-badge">快速心相报告</span>
      <h1>「五梦七心相」</h1>
      <p class="header-subtitle">分析时间：[日期]</p>
      <div class="dream-tags">
        <span class="dream-tag">[梦型标签]</span>
      </div>
    </header>

    <!-- 五梦归类（精简） -->
    <section class="dream-classification">
      <h2 class="dream-classification-title">五梦归类</h2>
      <div class="dream-classification-item">
        <div class="dream-classification-label">梦型判定</div>
        <div class="dream-classification-content">[梦型判定结果]</div>
      </div>
    </section>

    <!-- 心相一：欲望之镜 -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">一</span>
          <h2 class="heart-mirror-title">欲望之镜</h2>
          <span class="heart-mirror-label">核心动机</span>
        </div>
        <div class="heart-mirror-content">
          <p>[欲望之镜分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 心相三：意象之林 -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">三</span>
          <h2 class="heart-mirror-title">意象之林</h2>
          <span class="heart-mirror-label">关键象征</span>
        </div>
        <div class="heart-mirror-content">
          <p>[意象之林分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 心相七：行动之引 -->
    <section class="heart-mirror">
      <div class="heart-mirror-card">
        <div class="heart-mirror-header">
          <span class="heart-mirror-number">七</span>
          <h2 class="heart-mirror-title">行动之引</h2>
          <span class="heart-mirror-label">实践指引</span>
        </div>
        <div class="heart-mirror-content">
          <p>[行动之引分析内容]</p>
        </div>
      </div>
    </section>

    <!-- 吉凶参考（仅玄学框架） -->
    <section class="fortune-reference">
      <h2 class="fortune-reference-title">☯ 吉凶参考</h2>
      <div class="fortune-reference-content">
        <p><span class="fortune-good">近期宜：</span>[行动建议]</p>
        <p><span class="fortune-caution">近期忌：</span>[注意事项]</p>
      </div>
      <p class="fortune-reference-note">* 以上仅为传统解读参考，你的行动和心态才是决定因素。</p>
    </section>

    <!-- 综合心语 -->
    <section class="closing-wisdom">
      <h2 class="closing-wisdom-title">综合心语</h2>
      <p class="closing-wisdom-text">
        [综合心语内容]
      </p>
    </section>

    <!-- 梦境日记建议 -->
    <section class="dream-diary">
      <h2 class="dream-diary-title">🌙 梦境日记建议</h2>
      <div class="dream-diary-content">
        <p>如果你想持续探索自己的梦境世界，可以试试这个方法：</p>
        <ol>
          <li>每天醒来后，花1分钟记录梦境关键词</li>
          <li>一周后回顾，看看有没有重复出现的主题</li>
          <li>一个月后再次解读，发现更深层的心理模式</li>
        </ol>
      </div>
    </section>

    <!-- 分享引导 -->
    <div class="share-guide">
      <p class="share-guide-text">这份报告属于你。如果想分享给朋友，可以截图保存。你的梦境，你的心相。</p>
    </div>

    <!-- 分享卡片 -->
    <section class="share-card">
      <span class="share-card-badge">五梦七心相</span>
      <p class="share-card-dream-type">[梦型标签]</p>
      <p class="share-card-keyword">「[核心意象词]」</p>
      <p class="share-card-message">[一句话心语]</p>
      <p class="share-card-footer">— 五梦七心相 · 快速心相报告</p>
    </section>

    <!-- 用户反馈 -->
    <section class="feedback-section">
      <h2 class="feedback-title">这份解读对你有帮助吗？</h2>
      <div class="feedback-options">
        <div class="feedback-option">💡 很有帮助，让我更了解自己</div>
        <div class="feedback-option">🌱 有一些启发，但还想深入了解</div>
        <div class="feedback-option">💭 和我的感受不太一样，想再聊聊</div>
      </div>
    </section>

    <!-- 底部 -->
    <footer class="footer">
      <p class="footer-text">心相之道，在于观象见心，以梦为镜</p>
    </footer>
  </div>
</body>
</html>
```

## 七、分享卡片模板

分享卡片嵌入在报告底部，也可单独生成供用户截图分享。

**设计规范**：
- 宽度：375px（适合手机截图）
- 背景：深色渐变（深墨色 → 灰墨色），与报告形成反差
- 内容：梦型标签 + 核心意象词 + 一句话心语
- 底部：品牌标识 "五梦七心相 · 心相分析报告"

**CSS 样式**：见深度模式模板中的 `.share-card` 相关样式

## 八、报告内容撰写规范

### 1. 各部分内容要求

**五梦归类**：
- 梦型判定：判定梦型（正梦/噩梦/思梦/寤梦/喜梦/惧梦），简要说明依据
- 梦日溯源：近期印象（梦日关键事件）+ 躯体刺激（睡眠身体感觉）

**七心相解析**：
- 心相一：核心动机分析（3-4句，指出梦在满足什么欲望）
- 心相二：情绪线索分析（3-4句，描述情感如何流动）
- 心相三：关键象征解读（每个核心意象2-3句）
- 心相四：人物映射分析（每个关键人物2-3句）
- 心相五：未解情结分析（3-4句，指出内心在纠结什么）
- 心相六：传统视角解读（3-4句，应用象数方法）
- 心相七：实践指引（2-3个具体建议或反思方向）

**综合心语**：
- 一段话总结，温暖柔和，50-80字

### 2. 长度要求

**深度模式报告**：
- 整体报告：800-1500字（不含HTML标签）
- 单个心相：80-150字
- 综合心语：50-80字

**快速模式报告**：
- 整体报告：400-600字（不含HTML标签）
- 单个心相：60-100字
- 综合心语：30-50字

## 九、吉凶参考撰写规范

### 1. 何时显示
- 仅在用户选择玄学框架或双框架结合时显示
- 心理学框架的报告不包含此区块

### 2. 内容要求
- **近期宜**：1-2条基于卦象和梦型的正面行动建议
- **近期忌**：1-2条基于卦象和梦型的注意事项
- **附注**：必须包含"以上仅为传统解读参考，你的行动和心态才是决定因素"

### 3. 语气要求
- 使用温和、建议性语气
- 避免绝对化表达（"必定""一定会"）
- 使用"可能提示""或许可以""建议"等柔性表达

### 4. 示例

```
☯ 吉凶参考

近期宜：聚焦行动，将焦虑转化为具体准备。坎卦提示"行有尚"，只要行动，必有收获。
近期忌：过度犹豫不决。坎离相冲提示当前是关键转折点，拖延可能错失时机。

* 以上仅为传统解读参考，你的行动和心态才是决定因素。
```

## 十、报告禁止事项

- ❌ "此梦主..."（武断）
- ❌ "必须""应该"（命令）
- ❌ 纯学术术语堆砌
- ❌ 纯黑 `#000` / 纯白 `#fff`
- ❌ Inter/Roboto/Arial 默认字体
- ❌ 卡片嵌套卡片
- ❌ 紫蓝渐变背景
- ❌ bounce/elastic 动画
- ❌ 吉凶参考中使用绝对预测性语言

## 十一、报告推荐语气

| 场景 | 推荐表达 |
|------|----------|
| 描述梦境 | 「这个画面」而非「这个事件」 |
| 解读动机 | 「也许...」「似乎...」「你的潜意识似乎在...」 |
| 提供建议 | 「可以考虑...」「或许可以试试...」 |
| 玄学视角 | 「传统解读认为...」「象数之机暗示...」 |
| 吉凶参考 | 「可能提示...」「或许可以...」「建议...」 |
| 总结 | 「综合来看...」「双视角都指向...」 |
| 梦境日记 | 「坚持记录，你会慢慢读懂它的语言」 |
| 分享引导 | 「这份报告属于你。你的梦境，你的心相。」 |
