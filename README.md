# 量潮叙事工程案例

叙事工程案例库，按体裁（genre）分类，每个体裁下按作品风格（style）分目录管理。

## 目录结构

```
gallery/
├── fiction/              # 小说
│   ├── urban-romance/    # 都市言情 — 克制浪漫
│   │   ├── style.yaml    # 风格模型（10 维度）
│   │   └── sample.md     # 风格样本（精选片段）
│   └── campus-romance/   # 校园言情 — 校园轻甜
│       └── style.yaml    # 风格模型（10 维度）
└── README.md
```

## 组织规则

**第一层 — 体裁（genre）**

按文学体裁分大类：`fiction/`（小说）、`drama/`（戏剧）、`essay/`（散文）等。每种体裁在 gallery 根目录下创建一个目录。

**第二层 — 风格子目录**

每部作品或每个独立的风格体系，在所属体裁下创建一个目录。目录名使用英文 kebab-case，体现**场景类型**而非风格名称：

| 目录名 | 场景 | style.yaml 中的 model.title |
|--------|------|---------------------------|
| `urban-romance` | 都市言情 | 克制浪漫 |
| `campus-romance` | 校园言情 | 校园轻甜 |

目录名回答"这是什么类型的作品"，`model.title` 回答"这是什么风格"。

**每个风格子目录包含的文件**

| 文件 | 必选 | 说明 |
|------|------|------|
| `style.yaml` | ✅ | 10 维度的风格模型，含 `dimensions`、`examples` |
| `sample.md` | ❌ | 精选样本片段，供 LLM 参考。可选，有则更佳 |

**style.yaml 结构**

```yaml
model:
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

examples:
  - paragraph: |-              # 代表性段落
      原文...
    dimension: 所属维度名称
    note: 为什么选这段
```

10 个固定维度：总体风格定位、叙事视角、时间结构、语言风格、情感表达、细节美学、人物塑造、叙事节奏、流行文化嵌入、整体美学。

**新增作品流程**

1. 确认所属体裁（gallery 根目录下是否有对应的目录，没有则新建）
2. 在该体裁下新建风格子目录，取英文 kebab-case 名称
3. 按照上述结构编写 `style.yaml`
4. 可选：从作品中精选片段写入 `sample.md`
5. 提交并推送
