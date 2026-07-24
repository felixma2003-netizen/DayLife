# DayLife

A beautiful desktop daily & command daily app built with Electron + React + TypeScript.

> 记录每一天 — Capture your daily life with markdown journals, mood tracking, schedules, and a WindTerm-style command recorder.

## Features

### Journal Editor

- **Markdown editing** with live split-screen preview
- **28 built-in templates** across 7 categories (Travel, Work, Essay, Study, Life, Idea, Other)
- **Format toolbar** — bold, italic, headings, lists, code blocks, quotes, links, tables
- **Mood tracker** — 5 mood levels with emoji
- **Weather picker** — 8 weather conditions
- **Word count** & reading time estimate
- **Image paste** support (Ctrl+V)

### Calendar & Stats

- **Heatmap calendar** — GitHub-style activity visualization
- **Monthly view** with daily entry indicators
- **Statistics panel** — total entries, streaks, category breakdown

### Terminal View (Command Recorder)

- **WindTerm-style dark terminal** UI
- **SecureCRT-inspired keyword highlighting** — error (red), warning (yellow), success (green), security (cyan)
- **Multi-line editing** — write an entire article of commands, then save as one entry
- **Batch delete** — select multiple entries and delete with confirmation
- **Live preview** with syntax highlighting as you type
- **Command search** across all saved entries

### Schedules

- **Precise scheduling** — year/month/day/hour/minute
- **Category-colored** schedule items
- **Quick-add** from the sidebar

### AI Integration

- **OpenAI-compatible API** support (DeepSeek, ChatGPT, etc.)
- **Smart summary** — AI-generated daily log summaries
- **Writing prompts** — get inspired when you're stuck
- **Intelligent recall** — search past entries with natural language
- **Chinese-English translation** — one-click translation button

### Other Features

- **Light / Dark theme** — Tokyo Night color scheme for dark mode
- **i18n** — Full Chinese & English interface (switchable in Settings)
- **Backup & Restore** — Export/import all data as JSON
- **Export** — Markdown, PDF, Xmind formats
- **LocalStorage persistence** — No server needed, data stays on your device

## Tech Stack

| Layer    | Technology                                  |
| -------- | ------------------------------------------- |
| Frontend | React 18, TypeScript 5, Vite 5              |
| Styling  | Tailwind CSS 3                              |
| Desktop  | Electron 31                                 |
| Markdown | marked.js                                   |
| Export   | jsPDF (PDF), JSZip (Xmind), plain text (MD) |
| Date     | dayjs                                       |
| i18n     | Custom React Context system                 |

## Getting Started

### Prerequisites

- **Node.js** >= 18
- **npm** (comes with Node.js)

### Installation

```bash
# Clone the repository
git clone https://github.com/felixma2003-netizen/DayLife.git
cd daylife

# Install dependencies
npm install
```

### Development

```bash
# Start Vite dev server (web only)
npm run dev

# Build & run as Electron desktop app
npm run electron:dev
```

### Build for Production

```bash
# Build the web assets
npm run build

# Package as Windows executable
npm run electron:build
```

The built executable will be in `release/`.

## Project Structure

```
daylife/
├── electron/              # Electron main process
│   ├── main.cjs           # Main process entry
│   ├── preload.cjs        # Preload script
│   ├── icon.ico           # Windows icon
│   └── icon.png           # App icon
├── src/
│   ├── components/        # React components (17 files)
│   │   ├── AIPanel.tsx         # AI assistant panel
│   │   ├── BackupRestore.tsx   # Data backup & restore
│   │   ├── Calendar.tsx        # Heatmap calendar
│   │   ├── CategorySelector.tsx
│   │   ├── Editor.tsx          # Markdown editor with templates
│   │   ├── ExportPanel.tsx     # Export to MD/PDF/Xmind
│   │   ├── Logo.tsx            # App logo (SVG)
│   │   ├── MoodTracker.tsx     # Mood selector
│   │   ├── SchedulePanel.tsx   # Schedule management
│   │   ├── SearchBar.tsx       # Global search
│   │   ├── SettingsPanel.tsx   # Settings (AI, font, language)
│   │   ├── StatsPanel.tsx      # Statistics
│   │   ├── TerminalView.tsx    # Command recorder (WindTerm-style)
│   │   ├── ThemeSwitcher.tsx   # Light/Dark toggle
│   │   ├── TodoList.tsx        # Todo checklist
│   │   ├── TranslateButton.tsx # CN-EN translation
│   │   └── WeatherPicker.tsx   # Weather selector
│   ├── utils/             # Utility functions
│   │   ├── ai.ts               # AI API client
│   │   ├── dateUtils.ts        # Date formatting
│   │   ├── exportMarkdown.ts   # MD export
│   │   ├── exportPDF.ts        # PDF export
│   │   ├── exportXmind.ts      # Xmind export
│   │   ├── highlighter.ts      # Command syntax highlighter
│   │   └── storage.ts          # LocalStorage CRUD
│   ├── types/
│   │   └── index.ts            # TypeScript types & constants
│   ├── App.tsx                 # Root component
│   ├── i18n.tsx                # Internationalization system
│   ├── index.css               # Global styles & theme variables
│   └── main.tsx                # React entry point
├── index.html                  # HTML template
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── vite.config.ts
```

## Keyboard Shortcuts

| Shortcut | Action                    |
| -------- | ------------------------- |
| `Ctrl+V` | Paste image into editor   |
| `Ctrl+B` | Bold (in editor)          |
| `Ctrl+S` | Save current log          |
| `Tab`    | Indent in terminal editor |

## Configuration

Open **Settings** (gear icon in top-right) to configure:

- **AI API** — Set endpoint URL, API key, model name (OpenAI-compatible)
- **Language** — Chinese / English
- **Font size** — Adjust editor font size
- **Storage directory** — View data location

## Data Storage

All data is stored locally in your browser's `localStorage`. No data is sent to any server unless you configure AI features. Use **Backup & Restore** to export/import your data as a JSON file.

## Acknowledgments

- [React](https://react.dev/)
- [Electron](https://www.electronjs.org/)
- [Vite](https://vitejs.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [marked.js](https://marked.js.org/)
- [Tokyo Night](https://github.com/enkia/tokyo-night-vscode-theme) color inspiration
