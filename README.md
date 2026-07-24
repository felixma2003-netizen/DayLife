# DayLife

一款精致的桌面日志与命令记录工具，基于 Electron + React + TypeScript 构建。

> 记录每一天 — 用 Markdown 写日志、追踪心情、管理日程，还能在 WindTerm 风格的终端中记录命令。

## 功能特性

### 日志编辑器

- **Markdown 编辑**，支持分屏实时预览
- **28 个内置模板**，覆盖 7 个分类（旅行、工作、随笔、学习、生活、想法、其他）
- **格式工具栏** — 加粗、斜体、标题、列表、代码块、引用、链接、表格
- **心情打卡** — 5 个心情等级，配 emoji 表情
- **天气选择** — 8 种天气状况
- **字数统计** & 预计阅读时间
- **图片粘贴** 支持（Ctrl+V）

### 日历与统计

- **热力图日历** — GitHub 风格的活动可视化
- **月度视图**，每日条目一目了然
- **统计面板** — 总条目数、连续打卡天数、分类占比

### 终端视图（命令记录器）

- **WindTerm 风格暗色终端** UI
- **SecureCRT 风格关键词高亮** — error（红色）、warning（黄色）、success（绿色）、security（青色）
- **多行整篇编辑** — 写完一整篇命令后，统一保存为一条记录
- **批量删除** — 多选命令条目，一键确认删除
- **实时预览** — 输入时即可看到语法高亮效果
- **命令搜索** — 跨所有已保存条目检索

### 日程安排

- **精确到分钟** — 年/月/日/时/分
- **分类配色** — 不同类别的日程用颜色区分
- **侧边栏快速添加**

### AI 助手

- **兼容 OpenAI 接口** — 支持 DeepSeek、ChatGPT 等
- **智能摘要** — AI 自动生成日志总结
- **写作灵感** — 卡壳时给你灵感提示
- **智能回忆** — 用自然语言搜索过去的日志
- **中英互译** — 一键翻译按钮

### 其他功能

- **亮色 / 暗色主题** — 暗色模式采用 Tokyo Night 配色
- **国际化** — 支持中文 / 英文界面切换（在设置中切换）
- **备份与恢复** — JSON 格式导出/导入全部数据
- **多格式导出** — Markdown、PDF、Xmind
- **本地存储** — 数据保存在 localStorage，无需服务器，隐私安全

## 技术栈

| 层级     | 技术                                       |
| -------- | ------------------------------------------ |
| 前端框架 | React 18, TypeScript 5, Vite 5             |
| 样式     | Tailwind CSS 3                             |
| 桌面端   | Electron 31                                |
| Markdown | marked.js                                  |
| 导出     | jsPDF（PDF）、JSZip（Xmind）、纯文本（MD） |
| 日期     | dayjs                                      |
| 国际化   | 自研 React Context 方案                    |

## 快速开始

### 环境要求

- **Node.js** >= 18
- **npm**（随 Node.js 一起安装）

### 安装

```bash
# 克隆仓库
git clone https://github.com/你的用户名/daylife.git
cd daylife

# 安装依赖
npm install
```

### 开发调试

```bash
# 启动 Vite 开发服务器（仅网页）
npm run dev

# 构建并以 Electron 桌面应用运行
npm run electron:dev
```

### 生产打包

```bash
# 构建前端资源
npm run build

# 打包为 Windows 可执行文件
npm run electron:build
```

打包产物输出到 `release/` 目录。

## 项目结构

```
daylife/
├── electron/              # Electron 主进程
│   ├── main.cjs           # 主进程入口
│   ├── preload.cjs        # 预加载脚本
│   ├── icon.ico           # Windows 图标
│   └── icon.png           # 应用图标
├── src/
│   ├── components/        # React 组件（17 个）
│   │   ├── AIPanel.tsx         # AI 助手面板
│   │   ├── BackupRestore.tsx   # 数据备份与恢复
│   │   ├── Calendar.tsx        # 热力图日历
│   │   ├── CategorySelector.tsx
│   │   ├── Editor.tsx          # Markdown 编辑器（含模板）
│   │   ├── ExportPanel.tsx     # 导出 MD/PDF/Xmind
│   │   ├── Logo.tsx            # 应用 Logo（SVG）
│   │   ├── MoodTracker.tsx     # 心情选择器
│   │   ├── SchedulePanel.tsx   # 日程管理
│   │   ├── SearchBar.tsx       # 全局搜索
│   │   ├── SettingsPanel.tsx   # 设置（AI、字体、语言）
│   │   ├── StatsPanel.tsx      # 统计面板
│   │   ├── TerminalView.tsx    # 命令记录器（WindTerm 风格）
│   │   ├── ThemeSwitcher.tsx   # 亮/暗主题切换
│   │   ├── TodoList.tsx        # 待办清单
│   │   ├── TranslateButton.tsx # 中英翻译
│   │   └── WeatherPicker.tsx   # 天气选择器
│   ├── utils/             # 工具函数
│   │   ├── ai.ts               # AI API 客户端
│   │   ├── dateUtils.ts        # 日期格式化
│   │   ├── exportMarkdown.ts   # MD 导出
│   │   ├── exportPDF.ts        # PDF 导出
│   │   ├── exportXmind.ts      # Xmind 导出
│   │   ├── highlighter.ts      # 命令语法高亮
│   │   └── storage.ts          # LocalStorage 增删改查
│   ├── types/
│   │   └── index.ts            # TypeScript 类型与常量
│   ├── App.tsx                 # 根组件
│   ├── i18n.tsx                # 国际化系统
│   ├── index.css               # 全局样式与主题变量
│   └── main.tsx                # React 入口
├── index.html                  # HTML 模板
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── vite.config.ts
```

## 截图

> 上传到 GitHub 后在此添加截图：
>
> `![Uploading image.png…]()
`
> `![终端](screenshots/terminal.png)`
> `![日历](screenshots/calendar.png)`

## 快捷键

| 快捷键   | 功能             |
| -------- | ---------------- |
| `Ctrl+V` | 粘贴图片到编辑器 |
| `Ctrl+B` | 加粗（编辑器中） |
| `Ctrl+S` | 保存当前日志     |
| `Tab`    | 终端编辑器中缩进 |

## 配置说明

点击右上角 **设置**（齿轮图标）进行配置：

- **AI API** — 设置接口地址、API Key、模型名称（兼容 OpenAI 格式）
- **语言** — 中文 / English
- **字体大小** — 调整编辑器字体
- **存储目录** — 查看数据存储位置

## 数据存储

所有数据保存在浏览器的 `localStorage` 中。除非你配置并使用了 AI 功能，否则不会有任何数据发送到服务器。可以使用 **备份与恢复** 功能将数据导出为 JSON 文件或从文件恢复。

## 软件下载

| 版本   | 百度网盘链接        | 提取码 |
| -------- | ---------------- | -----------------|
| DayLife | https://pan.baidu.com/s/1t3qFVdVtCTMir5Dtt9lPKA | d925 |

## Acknowledgments

- [React](https://react.dev/)
- [Electron](https://www.electronjs.org/)
- [Vite](https://vitejs.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [marked.js](https://marked.js.org/)
- [Tokyo Night](https://github.com/enkia/tokyo-night-vscode-theme) color inspiration
