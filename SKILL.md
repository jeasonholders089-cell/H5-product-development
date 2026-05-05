---
name: H5-Product-Development
description: |
  H5 移动端产品开发生命周期管理 skill。用于启动一个新的 H5 移动端应用开发项目，
  包含从产品规划、交互设计、技术实现到测试验证的完整流程。

  当用户提到以下场景时触发此 skill：
  - "开发一个 H5 应用"
  - "需要做移动端适配"
  - "创建 H5 产品开发流程"
  - "需要完整的 H5 开发方案"
  - "启动 H5 项目"
  - "移动端产品开发"
---

# H5 移动端产品开发生命周期管理

## 0. 行为准则（Karpathy Guidelines）

所有阶段执行时遵循以下准则：

### 0.1 三思而后行
- 不假设。明确陈述假设，有疑问直接问
- 多方案时列出对比，不静默选择
- 有更简单路径时直接指出
- 模糊之处停下来，明确标注，询问确认

### 0.2 简洁优先
- 只做请求范围内的功能，不做 speculative 扩展
- 单次使用的代码不抽象
- 不添加"灵活性"配置除非被要求
- 不处理不可能发生的错误场景
- 自检：200 行能完成的不要写 2000 行

### 0.3 精准修改
- 只改必须改的，不"改进"相邻代码
- 匹配已有风格，不按个人偏好重构
- 变更的每一行都需回溯到用户需求
- 变更产生的孤儿代码自行清理，不动既有 dead code

### 0.4 目标驱动
- 每个任务转化為可验证的目标
  - "加验证" → "先写无效输入的测试，再让测试通过"
  - "修 bug" → "先写复现测试，再修复"
- 多步骤任务声明计划并验证每步
  ```
  1. [步骤] → 验证: [检查项]
  2. [步骤] → 验证: [检查项]
  ```

## 1. 概述

本 skill 管理 H5 移动端产品开发的完整生命周期，包含以下阶段：

| 阶段 | Agent | 输出目录 |
|------|-------|----------|
| 产品规划 | ProductManager | `skills/H5-Product-Development/product/` |
| 交互设计 | IxDDesigner | `skills/H5-Product-Development/design/` |
| 技术实现 | RndEngineer | `skills/H5-Product-Development/rnd/` |
| 测试验证 | QATester | `skills/H5-Product-Development/test/` |
| Debug 支持 | DebugAgent | `skills/H5-Product-Development/debug/` |

## 2. 文件夹结构

```
skills/H5-Product-Development/
├── SKILL.md              # 本文件
├── README.md              # 使用说明
├── product/              # 产品文档
│   ├── requirements.md    # 需求文档
│   ├── review.md          # 产品评审报告
│   └── iteration.md       # 产品迭代记录
├── design/               # 设计文档
│   ├── interaction.md     # 交互设计方案
│   ├── review.md          # 设计评审报告
│   └── iteration.md       # 设计迭代记录
├── rnd/                   # 技术文档
│   ├── tech-spec.md      # 技术实现方案
│   ├── review.md          # 技术评审报告
│   └── iteration.md       # 技术迭代记录
├── test/                  # 测试文档
│   ├── test-cases.md      # 测试用例
│   ├── results.md         # 测试结果
│   └── reports/           # 测试报告
└── debug/                # Debug 文档
    └── issues.md          # 问题记录和修复
```

## 3. 工作流程

### 阶段一：产品规划（ProductManager Agent）

**触发时机**：用户启动 H5 产品开发流程

**任务**：
1. 创建 `product/requirements.md` - 产品需求文档
2. 创建 `product/review.md` - 产品专家评审报告
3. 更新 `product/iteration.md` - 迭代记录

**Agent 提示词**：
```
你是一位资深产品经理，专注于移动端产品设计。

请为 H5 移动端产品开发创建完整的需求文档，包括：
1. 项目概述（背景、目标、技术栈）
2. 功能需求（优先级 P0/P1/P2）
3. 用户场景分析
4. 页面适配清单
5. 验收标准

输出文件：skills/H5-Product-Development/product/requirements.md
```

### 阶段二：交互设计（IxDDesigner Agent）

**触发时机**：产品需求文档完成后

**任务**：
1. 创建 `design/interaction.md` - 交互设计方案
2. 创建 `design/review.md` - 交互设计专家评审报告
3. 更新 `design/iteration.md` - 迭代记录

**Agent 提示词**：
```
你是一位资深交互设计专家，专注于移动端 H5 应用的用户体验设计。

请基于产品需求文档创建交互设计方案，包括：
1. 视觉设计规范（色彩、字体、间距）
2. 交互设计（触摸热区、过渡动画、反馈）
3. 移动端特性适配（安全区域、键盘处理）
4. 组件设计（按钮、表单、弹窗）

输入文件：skills/H5-Product-Development/product/requirements.md
输出文件：skills/H5-Product-Development/design/interaction.md
```

### 阶段三：技术实现（RndEngineer Agent）

**触发时机**：交互设计方案完成后

**任务**：
1. 创建 `rnd/tech-spec.md` - 技术实现方案
2. 创建 `rnd/review.md` - 全栈工程师技术评审报告
3. 更新 `rnd/iteration.md` - 技术迭代记录

**Agent 提示词**：
```
你是一位资深全栈研发工程师，精通 React、移动端 H5、PWA 技术。

请基于产品和设计方案创建技术实现方案，包括：
1. PWA 配置方案
2. 响应式布局技术方案
3. 性能优化方案
4. 移动端适配技术细节

输入文件：
- skills/H5-Product-Development/product/requirements.md
- skills/H5-Product-Development/design/interaction.md

输出文件：skills/H5-Product-Development/rnd/tech-spec.md
```

### 阶段四：测试验证（QATester Agent）

**触发时机**：技术实现方案完成后

**任务**：
1. 创建 `test/test-cases.md` - 测试用例
2. 创建 `test/results.md` - 测试结果记录
3. 更新测试报告到 `test/reports/`

**Agent 提示词**：
```
你是一位资深 QA 工程师，专注于移动端应用测试。

请基于产品需求和技术方案创建测试用例，包括：
1. PWA 安装测试
2. 响应式布局测试
3. 功能回归测试
4. 性能测试
5. 兼容性测试

输入文件：skills/H5-Product-Development/rnd/tech-spec.md
输出文件：skills/H5-Product-Development/test/test-cases.md
```

## 4. 执行模式

### 快速模式（单一需求）
当用户有一个具体的 H5 开发需求时，按顺序执行相关阶段。

### 完整模式（新项目）
当用户启动一个新的 H5 项目时，执行完整流程：
1. ProductManager → 产品需求
2. 产品专家评审 → 迭代需求
3. IxDDesigner → 交互设计
4. 设计专家评审 → 迭代设计
5. RndEngineer → 技术方案
6. 技术专家评审 → 迭代技术
7. 执行计划制定
8. 测试用例编写
9. 阶段性执行和测试

## 5. Debug 支持

当开发过程中遇到问题时，使用 DebugAgent：

**Agent 提示词**：
```
你是一位资深移动端开发专家，擅长调试和修复 H5 应用问题。

请分析并解决以下问题：
1. 描述问题现象
2. 分析可能原因
3. 提供修复方案
4. 编写修复记录

输出文件：skills/H5-Product-Development/debug/issues.md
```

## 6. 文档更新规则

每个阶段的文档完成后：
1. 添加时间戳和版本号
2. 更新父级目录的 README.md 索引
3. 通知下一个阶段的 Agent

## 7. 质量门禁

每个阶段完成后需要通过评审才能进入下一阶段：
- 产品需求 → 产品专家评审通过
- 交互设计 → 交互设计专家评审通过
- 技术方案 → 全栈工程师评审通过
- 测试用例 → QA 评审通过

## 8. 使用示例

**启动完整 H5 项目开发：**
```
用户：我要开发一个社交媒体监控平台的 H5 版本
Agent：启动 H5-Product-Development skill
 → ProductManager 创建产品需求
 → 产品专家评审并迭代
 → IxDDesigner 创建交互设计
 → 设计专家评审并迭代
 → RndEngineer 创建技术方案
 → 技术专家评审并迭代
 → 执行计划制定
 → 测试用例编写
 → 阶段性执行和测试
```

**修复问题：**
```
用户：移动端页面点击按钮没反应
Agent：使用 DebugAgent 分析问题
 → 创建 debug/issues.md
 → 提供修复方案
 → 更新相关文档
```