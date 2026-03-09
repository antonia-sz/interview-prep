# JD + 简历 → 面试题预测助手

> 上传岗位描述（JD）和个人简历，AI 自动预测面试题，给出答题框架，分析匹配度，导出备考手册。

## ✨ 功能

- **三类面试题**：必问题（5）/ 针对性题（5）/ 追问题（5）= 共 15 道
- **STAR 答题框架**：每题配答题要点和关键词提示
- **匹配度分析**：量化评分 + 优势/弱点对照
- **备考建议**：具体可执行的准备策略
- **导出手册**：生成 Markdown 备考文档

## 🚀 使用方式

### 作为 OpenClaw Skill 使用

安装到 OpenClaw 后，直接对话：

```
JD：
[粘贴岗位描述]

简历：
[粘贴简历内容]
```

### 作为 CLI 工具使用

```bash
# 设置 API Key（DeepSeek 或 OpenAI 兼容接口）
export DEEPSEEK_API_KEY=your_key_here
# 或
export OPENAI_API_KEY=your_key_here

# 粘贴文本模式
python3 scripts/generate_questions.py \
  --jd "岗位描述文本" \
  --resume "简历文本"

# 文件模式（支持 PDF / DOCX / TXT）
python3 scripts/generate_questions.py \
  --jd /path/to/jd.txt \
  --resume /path/to/resume.pdf \
  --output ~/interview_prep.md

# 只解析文件内容
python3 scripts/parse_file.py /path/to/resume.pdf
```

## 📦 环境要求

```bash
pip install pdfplumber python-docx   # 可选，支持 PDF/DOCX 解析
```

无 `pdfplumber` 时自动 fallback 到纯文本输入。

## 📊 输出示例

```markdown
## 📊 匹配度分析
综合匹配度：**78%**

✅ 优势匹配项
- Python 5年经验 ↔ JD要求：Python 3年以上 ✓
- 带过5人团队 ↔ JD要求：有团队管理经验 ✓

⚠️ 待补强项
- JD 要求 Kubernetes 经验 → 简历未提及
- JD 强调客户沟通能力 → 案例偏少

## 📌 必问题
1. **请简单介绍一下你自己**
   - 准备30秒版 + 2分钟版
   - STAR：背景→技能→成就→匹配理由
...
```

## 📝 作者

[antonia-sz](https://github.com/antonia-sz) · Powered by OpenClaw

## 📄 License

MIT
