---
name: course-generator
description: >
  根据项目分析和用户画像，自动生成定制化的学习课程和指南。
  包括大纲制定、逐课填充、进度管理。
allowed-tools: Read, Write, Edit, Glob, Grep, WebFetch, WebSearch
---

# Course Generator - 课程生成技能

---

## 作用

这个技能在 `/learn` 工作流的第3-4阶段被调用。它的职责是：

1. 根据项目分析和用户画像生成课程大纲
2. 逐课填充详细内容
3. 管理学习进度
4. 同步进度到 CLAUDE.md

## 参考模板

- `01-outline-template.md` — 大纲模板
- `02-user-profile-template.md` — 用户画像模板

## 工作流程

### 1. 生成大纲

根据项目特点和用户学习场景，生成定制化大纲。

**输入：**
- 项目分析报告（来自 `/learn` 第1阶段）
- 用户画像（来自 `/learn` 第2阶段）

**输出：**
- 课程大纲（写入courses/[项目名]学习指南.md）
- progress.json
- CLAUDE.md 同步更新

### 2. 生成一课的内容

每次生成一课，包含：
- 学习目标（可衡量的结果）
- 学习内容（具体要读哪些文件、理解哪些概念）
- 重点文件清单
- 课后任务
- 完成标准

### 3. 更新进度

每完成一课：
- 更新 `progress.json`
- 更新 `CLAUDE.md` 中的进度表
