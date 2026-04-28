# D5 — 技能使用反思

> 完成时间：2026-04-27

---

## 我使用的技能

**技能1：`pdf`** — PDF 处理技能
**技能2：`bank-status` / `skill-dedup`** — neoskills 技能定义示例

---

## 任务描述

1. **pdf 技能**：读取并理解了 PDF 处理的完整 SKILL.md，涵盖合并/拆分/提取文本/提取表格/创建 PDF 等操作
2. **neoskills 技能**：阅读了 bank-status 和 skill-dedup 两个技能的 SKILL.md，理解了 Agent Skills 的标准格式

**解决的问题**：了解了技能是如何定义、触发和执行的，为未来使用/创建技能打下基础

---

## 产出物

### pdf 技能（SKILL.md 内容摘要）

```
核心操作：
- 合并PDF：PdfWriter.add_page()
- 拆分PDF：逐页写入新文件
- 提取文本：pdfplumber.extract_text()
- 提取表格：pdfplumber.extract_tables()
- 创建PDF：reportlab.lib
```

### neoskills 技能（SKILL.md 结构）

```markdown
---
name: skill-name
description: Use when user mentions...（触发条件）
---

# Skill Title

## Instructions / Quick Start
步骤1...
步骤2...

## Examples
具体示例...
```

---

## 技能工作原理

### 这个技能何时会被触发？

当用户说/提到：
- **pdf**：处理 PDF（读取、合并、拆分、提取）
- **bank-status**：查询技能库状态
- **skill-dedup**：去重、清理技能库

### 它的工作流程是什么？

1. **发现阶段**：智能体只加载技能的名称+描述（不占上下文）
2. **激活阶段**：匹配到任务时，读取完整 SKILL.md 到上下文
3. **执行阶段**：按指令执行，可调用 scripts/ 脚本

### 它能做什么？不能做什么？

| 技能 | ✅ 能做 | ❌ 不能做 |
|------|---------|----------|
| pdf | 合并/拆分/提取/创建PDF | 编辑复杂格式/处理加密PDF |
| bank-status | 查询技能库状态 | 修改/管理技能 |
| skill-dedup | 扫描重复/去重 | 自动判断相似性 |

---

## 反思

### 最惊讶的地方

**渐进式加载机制**：智能体启动时只加载技能名称+描述，不是把整个技能库都塞进上下文！这大大节省了 token 消耗，用到时才激活。

### 可能的改进方向

- 希望 pdf 技能能有"OCR 扫描文档"的完整示例（目前需要额外配置 tesseract）
- 希望 bank-status 能显示技能的"最后使用时间"，帮助清理不常用的技能

### 在我的专业中还能怎么用

1. **工商管理文献综述**：用 pdf 技能批量提取管理学期刊论文摘要，构建文献库
2. **商业报告模板**：用 docx 技能创建标准化商业计划书、可行性分析报告模板
3. **市场调研数据**：用 xlsx 技能处理问卷数据，生成统计图表

---

## 💡 代币消耗记录

本次消耗消息数：4 条（pdf技能加载 + neoskills阅读 + 对话 + 反思）
