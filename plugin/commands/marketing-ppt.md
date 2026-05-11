---
description: 医疗健康营销推广方案 PPT 一键生成。通过 Web Search 调研市场和竞品，结合营销方法论生成专业方案 PPT。
argument-hint: "<公司名> <产品名>"
disable-model-invocation: true
allowed-tools: WebSearch WebFetch Bash Read Write
---

# /marketing-ppt

医疗健康行业营销推广方案 PPT 一键生成器。输入公司名和产品名，自动完成市场调研、竞品分析、策略设计，输出 25-30 页专业方案 PPT。

## Trigger

用户运行 `/marketing-ppt` 或要求为医疗健康公司/产品生成营销推广方案 PPT。

## Inputs

从用户输入中提取：

1. **公司名**（必需）—— 医疗健康企业名称
2. **产品名**（必需）—— 具体产品/技术/疗法名称
3. **附加上下文**（可选）：
   - 产品阶段（导入期/成长期/成熟期）
   - 目标市场（科室/适应证/地域）
   - 预算范围（如有）
   - 已有资源（临床数据/医保编码/KOL 关系等）

如果用户只提供了公司名和产品名，直接进入执行流程，不做额外询问。

---

## 执行流程

### Phase 1: Web Search 市场调研

使用 Web Search 进行 5 类搜索，收集真实数据：

#### 1.1 公司与产品信息

搜索 query 模板：
- `"{公司名}" 官网 产品 技术`
- `"{产品名}" 临床数据 适应证`
- `"{公司名}" 融资 规模 团队`
- `"{产品名}" NMPA 注册证 分类`

**期望获取：**
- 公司定位、规模、融资阶段
- 产品技术原理、代际定位
- 临床数据（主要疗效指标、安全性、随访时长）
- 监管状态（注册证号、分类、获批适应证）
- 已有合规资质（ISO/GMP/质量体系）

#### 1.2 市场规模与患者数据

搜索 query 模板：
- `"{适应证}" 中国 患者数量 流行病学`
- `"{适应证}" 市场规模 增长率`
- `"{治疗领域}" 白皮书 流行病学数据`
- `"{适应证}" 未被满足的临床需求`

**期望获取：**
- 患者总量（用于 PPT Slide 02 的大数字）
- 年增长率
- 当前治疗渗透率（低渗透率 = 机会）
- 权威数据来源（白皮书/柳叶刀/指南）

#### 1.3 竞品分析

搜索 query 模板：
- `"{产品名}" 竞品 对比 同类产品`
- `"{治疗领域}" 中国 企业 产品 上市`
- `"{适应证}" 国产 进口 对比`
- `"{竞品名}" 临床数据 市场份额`

**期望获取：**
- 2-3 家直接竞品名称和定位
- 竞品临床数据对比
- 竞品准入状态（医保/物价）
- 竞品市场覆盖（手术例数/签约医院）
- 竞品营销策略（KOL/渠道/内容）

#### 1.4 政策与合规环境

搜索 query 模板：
- `"{产品名}" 医保编码 物价收录`
- `"{治疗领域}" DRG DIP 政策`
- `"{适应证}" 临床指南 专家共识 推荐`
- `医疗器械 "{分类}" 广告 合规 要求`

**期望获取：**
- 医保编码/物价收录状态
- 相关指南/共识中的推荐等级
- DRG/DIP 分组对支付的影响
- 行业监管动态

#### 1.5 行业趋势与学术动态

搜索 query 模板：
- `"{治疗领域}" 2024 2025 趋势 创新`
- `"{治疗领域}" 学术会议 中国`
- `"{产品名}" 论文 发表 临床试验`
- `"{治疗领域}" 国外 市场 对标`

**期望获取：**
- 行业发展趋势
- 关键学术会议和窗口期
- 国外对标企业/产品的市场表现（如美国同类产品营收）
- 技术发展方向

---

### Phase 2: 框架分析

基于 Phase 1 收集的数据，应用 4 个内部 skill 进行结构化分析：

#### 2.1 竞品分析（参考 skills/competitive-analysis/SKILL.md）

输出：
- 学术定位矩阵（技术代差/临床证据/指南收录/准入/覆盖/KOL 背书）
- 定位地图（X=证据强度，Y=准入进度）
- 核心机会 3-5 条
- 核心威胁 2-3 条
- 推荐行动

#### 2.2 推广策划（参考 skills/campaign-planning/SKILL.md）

输出：
- 战略判断（导入期/成长期的核心策略）
- 四层渠道系统组合
- KOL/KOC/种子三层分配
- 预算三档方案
- 12 个月 Roadmap
- 30/60/90 天行动计划

#### 2.3 绩效指标（参考 skills/performance-analytics/SKILL.md）

输出：
- 四层漏斗 KPI 体系
- 每层的目标值和归因方式
- 医生维度指标
- 报告频次建议

#### 2.4 内容创作（参考 skills/content-creation/SKILL.md）

输出：
- 三类内容模板（科普/访谈/纪实）
- 平台矩阵和权重
- 内容工厂 SOP
- 选题分类和样本

---

### Phase 3: PPT 内容编排

将 Phase 1-2 的数据和分析结果，按 [ppt-structure.md](../references/ppt-structure.md) 定义的 26 页模板编排为完整的 PPT 内容大纲。

**输出格式：** 逐页列出标题、正文内容、数据点、布局提示。此大纲作为 Phase 4 生成 PPT 的输入。

每页需要明确：
- 页面标题（中文 + 英文副标题）
- 核心数据/文案（从 Phase 1-2 提取的真实内容）
- 布局类型（参考 ppt-structure.md 中的 26 页结构定义）
- 数据来源标注

---

### Phase 4: 使用 PPTX Skill 生成演示文稿

**本阶段完全遵循 [skills/pptx/SKILL.md](../skills/pptx/SKILL.md) 的工作流。**

#### 4.1 阅读 pptxgenjs 创建指南

阅读 [skills/pptx/pptxgenjs.md](../skills/pptx/pptxgenjs.md) 获取完整的 pptxgenjs API 用法，包括：
- 文本、形状、表格、图表的创建方式
- 多行文本（breakLine）、列表（bullet）、富文本数组
- Slide Master 定义方式
- 字体、颜色、对齐、透明度等属性

#### 4.2 应用设计规范

遵循 [skills/pptx/SKILL.md](../skills/pptx/SKILL.md) 中的「Design Ideas」章节：

**配色选择 —— Midnight Executive（医疗专业感）：**
- Primary: `1E2761` (navy)
- Secondary: `CADCFC` (ice blue)
- Accent: `F96167` (coral，用于数据高亮)
- 深色背景页: `0D1B2A`
- 浅色内容页: `F8F9FA`

**字体：** Arial Black（标题）+ Calibri（正文）

**结构：** Dark/light 三明治结构 —— 深色封面 → 浅色内容 → 深色战略页 → 浅色详情 → 深色结尾

**布局多样性（pptx skill 要求）：**
- 不重复同一布局
- 每页必须有视觉元素（数据卡片/色块/图标/流程图）
- 大数据用 60-72pt Georgia
- 正文左对齐，标题居中
- NEVER 使用标题下划线（AI 生成特征）

#### 4.3 编写 pptxgenjs 脚本

按 Phase 3 大纲逐页编写 `generate-ppt.js`，参考 [ppt-structure.md](../references/ppt-structure.md) 中每页的布局代码模式。

关键约束：
- `pres.layout = "LAYOUT_16x9"`
- 定义 DARK_MASTER 和 LIGHT_MASTER 两种 Slide Master
- 页码格式 `{slideNum} / 26`
- 文件名 `{公司名}-{产品名}-营销推广方案.pptx`

#### 4.4 执行生成

```bash
npm init -y && npm install pptxgenjs
node generate-ppt.js
```

#### 4.5 QA 验证（pptx skill 强制要求）

**严格遵循 [skills/pptx/SKILL.md](../skills/pptx/SKILL.md) 的 QA 流程：**

**Step 1 — Content QA：**
```bash
python -m markitdown output.pptx
python -m markitdown output.pptx | grep -iE "\{.*\}|TBD|TODO|占位|xxxx|lorem"
```

**Step 2 — Visual QA（使用 subagent）：**
```bash
python skills/pptx/scripts/office/soffice.py --headless --convert-to pdf output.pptx
pdftoppm -jpeg -r 150 output.pdf slide
```

然后派发 subagent 进行视觉检查，检查清单：
- 元素重叠
- 文字溢出/截断
- 低对比度文字或图标
- 间距不均
- 边距不足（< 0.5"）
- 列对齐不一致

**Step 3 — Verification Loop：**
1. 发现问题 → 修复代码 → 重新生成
2. 重新验证受影响的页面
3. 直到一轮完整检查无新问题

**不完成至少一次 fix-and-verify 循环，不得宣称完成。**

---

## 设计参考

| 文件 | 用途 |
|------|------|
| [skills/pptx/SKILL.md](../skills/pptx/SKILL.md) | PPT 创建总入口、设计原则、QA 流程 |
| [skills/pptx/pptxgenjs.md](../skills/pptx/pptxgenjs.md) | pptxgenjs 完整 API 教程 |
| [references/ppt-structure.md](../references/ppt-structure.md) | 26 页结构模板、配色、Slide Master 代码 |
| [references/healthcare-frameworks.md](../references/healthcare-frameworks.md) | 医疗合规红线、KOL 分层、渠道特性 |

---

## 关键原则

1. **数据真实** —— 所有市场数据、患者数量、竞品信息必须来自 Web Search 真实结果，标注数据来源
2. **方法论驱动** —— 不是凭空编造策略，而是用 4 个 skill 的框架推导出具体方案
3. **行业合规** —— 所有内容须符合 healthcare-frameworks.md 中的合规要求，不出现禁忌表述
4. **一键完成** —— 整个流程自动执行，不中断询问用户
5. **中文优先** —— PPT 全部中文内容（英文仅作为副标题装饰），适配中文排版

---

## 输出

最终输出一个 `.pptx` 文件到当前工作目录，文件名格式：

```
{公司名}-{产品名}-营销推广方案.pptx
```

生成完成后告知用户：
- 文件路径
- PPT 页数
- 核心策略摘要（1-2 句话）
