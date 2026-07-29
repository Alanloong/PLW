# PLW — Project Learning Workflow

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![GitHub release](https://img.shields.io/badge/version-1.0.0-blue)]()
[![Claude Code](https://img.shields.io/badge/Claude%20Code-required-purple)](https://claude.ai/claude-code)

*让 Claude 帮你学习任何 GitHub 开源项目。*

🌐 其他语言版本：**🇨🇳 简体中文** | [🇺🇸 English](README-en.md)

> 作者是一名人文社科类研究生，计算机基础薄弱，为了搞懂 GitHub 上的项目做了这个工具。
> 如果你也是「小白」，这个项目可能适合你；如果你已经有经验，它的作用不大。

---

## 📖 这是什么

一个标准化的项目学习工作流框架。当你提供 GitHub 项目地址时，自动执行：

```
分析项目 → 了解用户 → 生成课程 → 逐课推进学习
```

课程以 Markdown（.md）文件输出，需要用支持预览的软件打开阅读。

---

## 📋 前置要求

- **Claude Code**（CLI）— AI 工作流引擎
- **Markdown 阅读器** — 用于阅读生成的课程文件

### 推荐的 Markdown 阅读器：Notepad++ + MarkdownViewerPlusPlus

生成的课程是 `.md` 格式，直接用记事本打开排版混乱。推荐安装 Notepad++ 并安装 Markdown 预览插件：

**第1步：下载安装 Notepad++**

前往官网下载安装包：
[https://notepad-plus-plus.org/downloads/](https://notepad-plus-plus.org/downloads/)

安装时选默认选项即可。

**第2步：安装 MarkdownViewerPlusPlus 插件**

```
方法一（推荐）：通过 Notepad++ 插件管理器安装
  打开 Notepad++ → 菜单栏「插件」→「插件管理」
  → 搜索 "MarkdownViewerPlusPlus" → 勾选 →「安装」

方法二：手动安装
  1. 下载插件：https://github.com/nea/MarkdownViewerPlusPlus/releases
  2. 将 _MarkdownViewerPlusPlus.dll_ 复制到 Notepad++ 的 plugins/ 文件夹
  3. 重启 Notepad++
```

安装后，打开 `.md` 文件，点击菜单「插件」→「MarkdownViewerPlusPlus」→「Preview」即可实时预览排版效果。

---

## 🚀 快速开始

```bash
# 1. 下载想学习的 GitHub 项目 zip
#    解压到 PLW/repos/ 文件夹
#    → repos/[项目名]-master/

# 2. 在 PLW 根目录启动 Claude Code
claude

# 3. 运行学习工作流
/learn https://github.com/用户名/项目名
```

### 工作流程

| 阶段 | 内容 | 产出 |
|------|------|------|
| 第1阶段 | 项目分析（deepwiki 速览 + 本地文件深入） | 项目分析报告 |
| 第2阶段 | 了解用户（学习场景 + 编程基础） | 用户画像 |
| 第3阶段 | 生成课程大纲 | 学习指南 + 进度文件 |
| 第4阶段 | 逐课填充 + 自动推进 | 完整课程 |

每学完一课，Claude 会**自动准备下一课**，不需要你手动提醒。

### 可选学习场景

```
① 快速上手 → 了解项目是干什么的，能快速用起来
② 学习原理 → 搞懂设计思路，借鉴到自己项目中
③ 掌握代码 → 从代码层面深入理解
```

---

## 📂 文件结构

```
PLW/
├── CLAUDE.md                   ★ 主配置 + 进度同步中心
├── repos/                      ★ 存放下载的 GitHub 项目
│   └── [项目名]-master/
├── courses/                    ★ 生成的课程文件（.md）
│   └── [项目名]学习指南.md
├── progress.json               ★ 机器可读的进度数据
├── feedback.json               ★ 学习特征记录
├── .claude/
│   ├── commands/
│   │   └── learn.md            ★ /learn 命令（核心入口）
│   ├── skills/
│   │   └── course-generator/   ★ 课程生成技能
│   └── settings.json
└── README.md
```

---

## 📄 课程文件说明

所有课程以 Markdown 格式输出到 `courses/` 文件夹，用 Notepad++ 打开后通过 MarkdownViewerPlusPlus 预览，效果如下：

- 标题层级清晰
- 表格对齐
- 代码块高亮
- 列表缩进正确

> `courses/` 中已包含一份 ai-job-search 的示例课程，可参考其格式。

---

## 💡 提示

- **项目分析越深入，课程质量越高**：Claude 会通过 deepwiki 和本地文件双重分析项目
- **用户画像越准确，课程越贴合**：第2阶段会了解你的编程基础和学习目标
- **课程会越用越懂你**：学习过程中 Claude 会默默观察你的学习特点，课程结束后可申请个性化优化
