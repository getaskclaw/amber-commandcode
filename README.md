# amber-commandcode

用私有题库 **AMBER** 实测 CommandCode（api.commandcode.ai）在售模型，只公开结果，不公开题目。
English: [README.en.md](README.en.md)

## 这是什么

- 「道」= 同一个模型名在不同家的卖场/接口；「案」= 一道题，「卷」= 一场考试记录（一案多卷 = 一道题的几个变体场次）。

- 每期一篇 `results/YYYY-Www.md`：同题、同 harness（跑考试并记分的程序），对目标模型跑全库；同名模型跨厂商并排。
- 一期固定报告：题集规模与哈希、每案找茬分（d2 分，我们的打分，算法不公开）与通过/失败、终端终态（程序跑完时的退出状态）、token 用量（若车道上报）与时延、环境指纹、按证据纪律写的定性裁决。
- 题目、oracle（判分器）、transcript（答题全过程记录）、中间产物**永不公开**（见下「发布纪律」）。
- 姐妹仓：[amber-deepseek](https://github.com/getaskclaw/amber-deepseek)（DeepSeek 官方道）、[amber-opencode](https://github.com/getaskclaw/amber-opencode)（OpenCode Go 道）、[amber-gpt](https://github.com/getaskclaw/amber-gpt)、[amber-crof](https://github.com/getaskclaw/amber-crof)、[amber-ollama](https://github.com/getaskclaw/amber-ollama)、[amber-devin](https://github.com/getaskclaw/amber-devin)、[amber-workbuddy](https://github.com/getaskclaw/amber-workbuddy)（WorkBuddy ACP 道）、[amber-doubao](https://github.com/getaskclaw/amber-doubao)、[amber-goldenpotato](https://github.com/getaskclaw/amber-goldenpotato)、[amber-kimi](https://github.com/getaskclaw/amber-kimi)、[amber-stepfun](https://github.com/getaskclaw/amber-stepfun)。本仓的对照轴是**同名模型跨厂商对决**——同一个模型名在 CommandCode / OpenCode Go / DeepSeek 官方道上可能是不同端点，跨仓引用一律带日期与档位声明。
- AMBER 是 agentic 实战题库（施工/运维/审查/视觉/需求漂移——题中要求中途变化），规范与制题工具见 [getaskclaw/amber](https://github.com/getaskclaw/amber)；考题本体私有。

## 发布纪律（红线）

1. 只发：分数与聚合、token 用量（若车道上报）、速度、定性裁决。
2. 永不发：题目内容、oracle/判分器、transcript、考生工作区、任何能复原题面的中间产物。
3. 每期必钉：模型 ID、effort 档（思考力度档位）、日期（UTC）、harness 版本、每案内容哈希（bundle_sha，每题内容的哈希指纹）。哈希用于对照 [amber](https://github.com/getaskclaw/amber) 的公开哈希清单，自证题集未变。
4. 案号与题目结构属私有面：公开结果里案例只用稳定别名（A-xxxxxxxx，哈希派生）+ bundle 哈希作句柄；内部案号、变体名、题目描述永不出现。
5. 基调：这是社区实测，不是对厂商的攻击。数据说话，措辞克制。

## 一个方法论前提

同名模型、同 provider，两次跑也可能不同分——推理参数、负载、服务端版本都在漂；转发/聚合道还隔着一层上游路由，同名不一定是同一个端点。所以这里的一切结论都带日期与档位，且定期重测。单日数字是快照，不是定律。

## 结果索引

| 期 | 内容 | 结论 |
|---|---|---|
| [2026-W37](results/2026-W37.md) | deepseek/deepseek-v4.1-flash 全库首考（23 案，GA 当日） | **17/23**（公共 21 案子集 15/21）；UI 搭建卷满分（全场第五家过案仓）；防御钉 8/9 刷新全员纪录；同名跨厂商三方对拍同为真 v4.1；审查/视觉面是弱项 |

> ⚠️ **三值化预览**（W38 更正特刊草稿 · 未签发 · 本草稿分支仅供审阅）：整数成绩将改写为「确认过 / 确认挂 / 挂起区间」。本仓：改判 0 格、挂起 14 格（挂起格只可能上移，补考前不计任何聚合、不给新名次）。另：假绿双向审计（WO-BRAIN）未开庭，现有 ✓ 格含「假及格」风险，特刊将如实标注。挂起 14 卷为案级计数口径。

## 免责

与 CommandCode、DeepSeek（深度求索）无任何隶属/赞助关系。分数是特定周、特定档位的快照，不构成采购建议。
