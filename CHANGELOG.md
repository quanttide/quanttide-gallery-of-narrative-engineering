# CHANGELOG

## [0.1.3] - 2026-06-03

### Added

- 新增共同提炼层：一级类别 `fiction/` 下新增 `motif.yaml` 和 `style.yaml`
- 都市言情新增 `motif.yaml`（5 母题）
- 校园言情新增 `motif.yaml`（4 母题）
- 都市言情新增 3 个样本场景：公园拥抱、酒吧表白、阳台看星星

### Changed

- 样本目录结构：单体 `sample.md` → `samples/` 多文件目录
- 都市言情样本从 5 场景合并文件拆为 8 个独立场景文件
- 校园言情样本体 `sample.md` → `samples/sample1.md` + `samples/sample2.md`
- 校园言情 `style.yaml` 和 `motif.yaml` 基于成稿内容更新
- `README.md` 更新为三级目录结构说明

## [0.1.2] - 2026-06-03

### Changed

- 移除 `model` 包装层级，根字段改为 `name/title/description`
- `name` 使用 slug（`urban-romance`、`campus-romance`），替代 UUID
- 更新 `README.md` 中的结构说明

## [0.1.1] - 2026-06-03

### Changed

- `style.yaml` 中的字段名 `examples` → `excerpts`，与 `sample.md` 区分（摘录 vs 完整场景）
- 二级类别目录名改为英文 kebab-case（`urban-romance`、`campus-romance`）
- `README.md` 术语统一为"一级类别/二级类别"

## [0.1.0] - 2026-06-03

初始化案例库。

### Added

- 建立 gallery 二级分类结构（一级类别 `fiction/` + 二级类别 `urban-romance/`、`campus-romance/`）
- 都市言情风格模型 `urban-romance/style.yaml`（10 维度 + 14 条示例）
- 都市言情风格样本 `urban-romance/sample.md`（5 场景精选片段）
- 校园言情风格模型 `campus-romance/style.yaml`（10 维度 + 6 条示例）
- 校园言情风格样本 `campus-romance/sample.md`（第五章完整场景）
- `README.md`：目录结构与组织规则说明
