# H5 移动端产品开发生命周期

> 本目录包含 H5 移动端产品开发的完整文档体系

## 目录结构

```
H5-Product-Development/
├── SKILL.md          # Skill 定义文件
├── README.md         # 本索引文件
├── product/          # 产品规划阶段
│   ├── requirements.md   # 需求文档
│   ├── review.md          # 评审报告
│   └── iteration.md       # 迭代记录
├── design/           # 交互设计阶段
│   ├── interaction.md     # 交互设计
│   ├── review.md          # 评审报告
│   └── iteration.md       # 迭代记录
├── rnd/              # 技术实现阶段
│   ├── tech-spec.md      # 技术方案
│   ├── review.md          # 评审报告
│   └── iteration.md       # 迭代记录
├── test/             # 测试验证阶段
│   ├── test-cases.md      # 测试用例
│   ├── results.md         # 测试结果
│   └── reports/           # 测试报告
└── debug/           # Debug 支持
    └── issues.md          # 问题记录
```

## 阶段进度

| 阶段 | 状态 | 负责人 | 完成时间 |
|------|------|--------|----------|
| 产品规划 | 待开始 | ProductManager | - |
| 交互设计 | 待开始 | IxDDesigner | - |
| 技术实现 | 待开始 | RndEngineer | - |
| 测试验证 | 待开始 | QATester | - |
| Debug 支持 | 待启用 | DebugAgent | - |

## 使用方法

### 启动新的 H5 项目
1. 创建项目需求 → `product/requirements.md`
2. 产品专家评审 → `product/review.md`
3. 创建交互设计 → `design/interaction.md`
4. 设计专家评审 → `design/review.md`
5. 创建技术方案 → `rnd/tech-spec.md`
6. 技术专家评审 → `rnd/review.md`
7. 制定执行计划
8. 编写测试用例 → `test/test-cases.md`
9. 阶段性执行和测试

### 查看项目状态
- 产品需求：查看 `product/requirements.md`
- 交互设计：查看 `design/interaction.md`
- 技术实现：查看 `rnd/tech-spec.md`
- 测试用例：查看 `test/test-cases.md`

### 问题修复
当遇到问题时，在 `debug/issues.md` 中记录并跟踪修复进度。

---

*最后更新：2026-05-05*
*Skill: H5-Product-Development v1.1 — 集成 Karpathy Guidelines*