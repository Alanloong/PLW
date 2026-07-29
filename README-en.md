# PLW — Project Learning Workflow

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Release](https://img.shields.io/github/v/release/Alanloong/PLW)](https://github.com/Alanloong/PLW/releases)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-required-purple)](https://claude.ai/claude-code)

*A Claude-powered workflow for learning any GitHub open-source project.*

🌐 Languages: [🇨🇳 简体中文](README.md) | **🇺🇸 English**

> The author is a humanities & social sciences graduate student with very basic computer skills. This tool is built for people in the same situation.
> If you're an experienced developer, this project may not be very useful to you.

---

## 📖 What is this

A standardized project-learning workflow. Give it a GitHub URL, and it automatically:

```
Analyze project → Profile user → Generate course → Learn lesson by lesson
```

Courses are output as Markdown (.md) files, which require a Markdown viewer to read properly.

---

## 📋 Prerequisites

- **Claude Code** (CLI)
- **A Markdown viewer** (e.g., Notepad++ with MarkdownViewerPlusPlus plugin)

---

## 🌐 For Non-Chinese Users

This project is configured to output courses in **Chinese** by default. To use it in English or your preferred language:

1. Open `CLAUDE.md`, find this line and delete or modify it:
   ```
   1. **全程使用中文沟通** — 所有回复、讲解、代码注释、课程内容全部用中文，禁止出现英文
   ```

2. Open `.claude/commands/learn.md`, find this line and delete or modify it:
   ```
   2. **全程中文沟通**
   ```

After these changes, Claude will communicate in your default language. The workflow logic stays unchanged.

---

## 🚀 Quick Start

1. Download PLW from [Releases page](https://github.com/Alanloong/PLW/releases) and extract it
2. Install Claude Code: `npm install -g @anthropic-ai/claude-code`
3. Download the GitHub project you want to learn, extract to `PLW/repos/`
4. Open terminal in the PLW folder, type `claude`
5. In Claude, type `/learn https://github.com/username/project`
6. Read the generated course in `PLW/courses/`

### Workflow

| Phase | Content | Output |
|-------|---------|--------|
| Phase 1 | Project analysis (deepwiki + local files) | Analysis report |
| Phase 2 | User profiling (learning scenario + skill level) | User profile |
| Phase 3 | Generate course outline | Study guide + progress file |
| Phase 4 | Fill lessons one by one | Complete course |

After each lesson, Claude **automatically prepares the next one**.

### Learning Scenarios

```
① Quick Start → Understand the project, get up and running fast
② Learn Principles → Understand the design patterns, apply to your own projects
③ Master Code → Deep code-level understanding
```

---

## 📂 Project Structure

```
PLW/
├── CLAUDE.md                   ★ Main config + progress sync
├── repos/                      ★ Downloaded GitHub projects
│   └── [project-name]-master/
├── courses/                    ★ Generated course files (.md)
│   └── [project-name]-guide.md
├── progress.json               ★ Machine-readable progress data
├── feedback.json               ★ Learning profile records
├── .claude/
│   ├── commands/
│   │   └── learn.md            ★ /learn command (core entry)
│   ├── skills/
│   │   └── course-generator/   ★ Course generator skill
│   └── settings.json
└── README.md
```

---

## 💡 Tips

- **Deeper project analysis = better courses**: Claude uses both deepwiki and local file analysis
- **Better user profile = more tailored courses**: Phase 2 profiles your skill level and goals
- **Courses adapt to you**: Claude silently observes your learning patterns and offers personalized optimization after completion

---

License: MIT
