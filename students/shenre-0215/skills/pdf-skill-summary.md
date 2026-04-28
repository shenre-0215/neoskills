# PDF 技能内容摘要

> 来源：WorkBuddy 内置 pdf 技能 SKILL.md
> 读取时间：2026-04-27

---

## 技能名称

`pdf` — PDF 文档处理技能

---

## 技能触发条件

当用户提到以下内容时触发：
- "读取 PDF"、"提取 PDF 内容"
- "合并 PDF"、"拆分 PDF"
- "PDF 转文字"、"PDF 提取表格"
- "创建 PDF"、"生成 PDF 报告"
- ".pdf" 文件相关操作

---

## 核心功能

| 功能 | 使用的库/工具 | 示例代码 |
|------|---------------|----------|
| 读取 PDF | `pypdf.PdfReader` | `reader = PdfReader("doc.pdf")` |
| 合并 PDF | `pypdf.PdfWriter` | `writer.add_page(page)` |
| 拆分 PDF | `pypdf.PdfWriter` | 逐页写入新文件 |
| 提取文本 | `pdfplumber` | `page.extract_text()` |
| 提取表格 | `pdfplumber` | `page.extract_tables()` |
| 创建 PDF | `reportlab` | `canvas.Canvas()` / `SimpleDocTemplate()` |
| OCR 扫描件 | `pytesseract` + `pdf2image` | 转图片后 OCR |
| 添加水印 | `pypdf` | `page.merge_page(watermark)` |
| 密码保护 | `pypdf` | `writer.encrypt()` |

---

## 工作流程

1. **加载 SKILL.md** → 了解可用操作
2. **确定任务类型** → 读取/合并/拆分/创建
3. **收集用户需求** → 文件路径、页码范围、输出格式
4. **执行操作** → 调用对应库
5. **返回结果** → 文件路径或提取内容

---

## 能力边界

### ✅ 能做
- 读取、合并、拆分 PDF
- 提取文本和表格
- 创建新 PDF 文档
- 添加水印、旋转页面
- 设置密码保护

### ❌ 不能做
- 编辑已有 PDF 的复杂格式
- 处理损坏的 PDF
- 直接处理扫描图片（需 OCR）
- 保留 PDF 中的表单填写内容

---

## 在工商管理专业中的应用场景

1. **商业文献综述**：批量提取管理学期刊论文摘要，构建文献库
2. **市场调研报告**：从 PDF 问卷或报告中提取结构化数据
3. **商业计划书模板**：生成标准化的 PDF 格式商业计划书模板
4. **课件与资料整理**：将多个 PDF 课件合并成一个学习资料包
