---
name: "visual-spec"
description: "Visual Requirement Analysis Skills for AI generators. Invoke when user needs to analyze requirements, generate specs, data models, prototypes, design details, acceptance cases, tests, and implementation inputs."
---

# visual-spec

## 何时调用

- 需要进行需求分析和规格说明
- 需要生成数据模型和可运行的原型
- 需要为每个功能生成详细设计规范
- 需要生成验收测试用例和自动化测试代码
- 需要生成集成的后端+前端实现代码
- 需要分析变更影响并更新工件
- 需要基于功能列表进行估算和计划

## 输出目标

- **需求分析**：生成背景、利益相关者、角色、术语、流程、场景、细节、依赖、功能列表和开放问题
- **解决方案验证**：生成数据模型、可运行的原型和场景审查页面
- **详细设计**：为每个功能生成 RBAC/数据权限/交互/验证/日志/通知/MQ/导入-导出/定时任务规范
- **验收和测试**：生成验收案例和自动化测试代码
- **集成实现**：生成后端+前端集成代码（与仓库的实际技术栈和约定对齐）
- **变更处理**：分析影响，更新工件，并生成变更日志
- **规划**：基于功能列表进行估算和计划（HTML输出）

## 命令

- `/vspec:new`：生成基线规范工件（写入到 /specs/）
- `/vspec:refine`：应用来自 /docs/refine/（或命令参数）的细化，并更新 /specs/details/ 和 /specs/prototypes/（需要现有的详细信息）
- `/vspec:refine-q`：将 questions.md 中已回答的项目合并回规范，并更新 /specs/background/original.md 中的规范需求
- `/vspec:detail`：为每个功能生成详细规范（写入到 /specs/details/）
- `/vspec:verify`：生成数据模型和按技术栈选择的可运行原型（根据 /scheme.yaml）（写入到 /specs/models/、/specs/prototypes/；需要非空的 /specs/details/）
- `/vspec:accept`：生成验收测试用例（写入到 /specs/acceptance/）
- `/vspec:test`：生成自动化测试代码（写入到仓库现有的测试目录或 /tests/）
- `/vspec:impl`：生成集成的后端+前端实现代码（写入到 /specs/ 下）
- `/vspec:upgrade`：基于 /docs/ 下的遗留+新输入（legacy/current/templates/texts/assets）进行升级/重新设计，生成/更新 /specs/，并将技术选择同步到 /scheme.yaml
- `/vspec:change`：分析并应用来自 /docs/change/ 的变更输入，更新工件，并写入 /specs/change_log.md（在更新前需要 git 快照提交）
- `/vspec:qc`：运行工件质量检查并写入报告（写入到 /specs/qc_report.md）
- `/vspec:plan`：生成估算和计划（写入到 /specs/plan/plan_estimate.md、/specs/plan/plan_schedule.html）

## 目录结构

- `skills/visual-spec-skill/SKILL.md`：技能定义和命令工作流程
- `skills/visual-spec-skill/prompts/`：每个命令使用的提示文件

## 最佳实践

- 定期更新技能库，添加新的技能和工具
- 为技能提供清晰的描述和使用示例
- 建立技能分类体系，方便查找和管理
- 鼓励团队成员贡献和分享技能
- 定期评估技能的有效性和相关性