# 量潮叙事工程案例

叙事工程案例库，按二级分类管理。

## 目录结构

```
gallery/
├── fiction/                    # 一级类别：小说
│   ├── motif.yaml              # 共同母题（跨作品）
│   ├── style.yaml              # 共同风格（跨作品）
│   │
│   ├── urban-romance/          # 二级类别：都市言情 — 克制浪漫
│   │   ├── style.yaml          # 风格模型（10 维度）
│   │   ├── motif.yaml          # 母题模型
│   │   └── samples/            # 风格样本（多场景独立文件）
│   │       ├── sample1.md
│   │       └── ...
│   │
│   └── campus-romance/         # 二级类别：校园言情 — 校园轻甜
│       ├── style.yaml
│       ├── motif.yaml
│       └── samples/
│           ├── sample1.md
│           └── sample2.md
│
└── README.md
```

## 组织规则

**一级类别**

按作品集合分大类，如 `fiction/`（小说）、`drama/`（戏剧）、`essay/`（散文），也可以是其他分类方式。每种一级类别在 gallery 根目录下创建一个目录。

一级类别下可放置共用的 `motif.yaml` 和 `style.yaml`，提炼该类别下多个作品的共同特征。

**二级类别**

每部作品或每个独立的风格体系，在所属一级类别下创建一个目录。目录名使用英文 kebab-case，体现场景类型：

| 目录名 | style `name` | style `title` |
|--------|-------------|-------------|
| `urban-romance` | `urban-romance` | 克制浪漫 |
| `campus-romance` | `campus-romance` | 校园轻甜 |

目录名与 `name` 字段一致。

**每个二级类别包含的文件**

| 文件 | 必选 | 说明 |
|------|------|------|
| `style.yaml` | ✅ | 风格模型，含 `dimensions`、`excerpts` |
| `motif.yaml` | ❌ | 母题模型，含 `motifs`（`title`、`description`、`weight`）|
| `samples/` | ❌ | 完整场景样本目录，每个场景一个独立 `.md` 文件 |

**style.yaml 结构**

```yaml
title: 风格名称              # 如"克制浪漫"
description: 一句话风格描述

dimensions:
  - title: 维度名称            # 10 个固定维度
    description: 该维度的详细描述（2-4 句，含具体场景和手法）
    confidence: 0.0-1.0        # 提炼确信度
    clues:                     # 支撑该判断的原文线索
      - 线索 1
      - 线索 2
    contradictions: []          # 反例（可选）

excerpts:
  - paragraph: |-              # 代表性短片段
      原文...
    dimension: 所属维度名称
    note: 为什么选这段
```

**motif.yaml 结构**

```yaml
title: 母题名称
description: 一句话概括

motifs:
  - title: 母题名
    description: 描述
    weight: 1-10
```

**samples/ 目录**

每个场景一个独立文件（`sample1.md`、`sample2.md` 等），包含完整场景节选。文件名按编号排序，不体现场景名（内容自述）。

## 固定维度

风格模型的 10 个固定维度：总体风格定位、叙事视角、时间结构、语言风格、情感表达、细节美学、人物塑造、叙事节奏、流行文化嵌入、整体美学。

母题模型不设固定维度，每个作品或类别提炼其特有的母题。

## 新增作品流程

1. 确认所属一级类别（gallery 根目录下是否有对应的目录，没有则新建）
2. 在该一级类别下新建二级类别目录，取英文 kebab-case 名称
3. 按照上述结构编写 `style.yaml` 和可选的 `motif.yaml`
4. 可选：从作品中精选场景写入 `samples/` 目录
5. 提交并推送
