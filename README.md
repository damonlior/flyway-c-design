# Flyway C Design

飞来汇（Flyway）C 端产品设计规范与 AI Design Skills。

本仓库面向飞来汇现有业务中的消费者 C 端页面，统一跨境收付款、换汇、个人账户、银行卡与支付工具、身份认证及交易安全等场景的设计语言、页面结构和 AI 设计执行流程。

## 仓库内容

主要规范包括：

- `AGENTS.md`：AI Agent 的总执行协议与任务边界
- `Design-System.md`：颜色、字体、间距、组件和设计 Token 规范
- `AI-Design-Skill.md`：AI 进行页面设计、评审和交付的方法
- `Pattern-Library.md`：首页、列表、详情、表单等页面结构模式

> 实际文件位置请以仓库中的目录结构为准。

## 使用方式

开始任务前，请以 `SKILL.md` 的 Reference Router 为准：先判断任务类型，再按需加载对应 reference 的具体章节，不要默认完整阅读全部规范文件。

完整设计依据为：

```text
Design-System.md
+ AI-Design-Skill.md
+ Pattern-Library.md
+ AGENTS.md
= 合规的飞来汇 C 端页面设计
```

## 基本原则

- 优先复用现有 Component、Variant、Variable 和 Style
- 使用语义化 Token，不直接使用任意颜色或尺寸
- 页面结构必须匹配 Pattern Library
- 使用 Auto Layout 构建可变内容
- 覆盖加载、错误、空状态、权限和风险状态
- 分别定义 Desktop、Compact Desktop 和 Mobile 行为
- 未经授权，不修改正式组件库和设计 Token
- 缺失能力应标记为 `Composition Pattern` 或 `Needs Extension`

## 适用范围

本规范适用于飞来汇现有业务中直接面向消费者的 C 端页面，包括：

- 跨境收款与付款的操作流程及结果页面
- 个人账户、余额与资金信息展示
- 换汇、汇率展示及汇率变化提醒
- 银行卡与支付工具的绑定、查看和使用
- 交易记录、订单详情及交易状态查询
- 个人身份认证（KYC）、资料提交与认证进度查询
- 登录、密码与验证码验证、交易安全提示及风险确认
- 引导、空状态、错误恢复与操作结果页面

## 目录结构

```text
flyway-c-design/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── AGENTS.md
    ├── AI-Design-Skill.md
    ├── Design-Document-Output-Rules.md
    ├── Design-System.md
    └── Pattern-Library.md
```

`SKILL.md` 为 skill 入口；`references/` 下为四份治理文档与 Figma 交付规则。
