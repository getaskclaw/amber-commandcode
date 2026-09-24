# amber-commandcode

用私有题库 **AMBER** 实测 CommandCode（可从它这里购买各家模型的 API 额度，api.commandcode.ai）在售模型：只公开成绩，不公开题目。
English: [README.en.md](README.en.md)

## 这是什么

我们定期让同一批模型考试，只发成绩单；考题和评分细节不公开。

![最新一期榜单构成（2026-W39）](results/assets/2026-W39-board.zh.png?v=20260923)

- 「道」= 一个模型名在某家平台的售卖入口（也可读作渠道）；「案」= 一道题；「卷」= 一场考试记录；「档」= effort 档，思考力度档位。
- 每期一篇 `results/YYYY-Www.md`：同题、同考试程序（harness，跑考试并记分的程序），对目标模型跑全库；同名模型跨平台并排。
- 一期固定报告：题集规模与哈希、每案找茬分（d2 分：我们对模型犯错种类与严重度的打分，算法不公开；过/不过关另看每案通过线）与通过/失败、终端终态（程序跑完时的退出状态）、token 用量（若渠道上报）与时延、环境指纹、按证据纪律写的定性裁决。
- 题目、oracle（判分器）、transcript（答题全过程记录）、中间产物**永不公开**（见下「发布纪律」）。
- 姐妹仓：[amber-deepseek](https://github.com/getaskclaw/amber-deepseek)（DeepSeek 官方道）、[amber-opencode](https://github.com/getaskclaw/amber-opencode)（OpenCode Go 道）、[amber-gpt](https://github.com/getaskclaw/amber-gpt)、[amber-crof](https://github.com/getaskclaw/amber-crof)、[amber-ollama](https://github.com/getaskclaw/amber-ollama)、[amber-devin](https://github.com/getaskclaw/amber-devin)、[amber-workbuddy](https://github.com/getaskclaw/amber-workbuddy)（WorkBuddy ACP 道）、[amber-doubao](https://github.com/getaskclaw/amber-doubao)、[amber-goldenpotato](https://github.com/getaskclaw/amber-goldenpotato)、[amber-kimi](https://github.com/getaskclaw/amber-kimi)、[amber-stepfun](https://github.com/getaskclaw/amber-stepfun)。本仓的对照轴是**同名模型跨厂商对决**——同一个模型名在 CommandCode / OpenCode Go / DeepSeek 官方道上可能是不同端点，跨仓引用一律带日期与档位声明。
- AMBER 是 agentic 实战题库（施工/运维/审查/视觉/需求漂移——题中要求中途变化），规范与制题工具见 [getaskclaw/amber](https://github.com/getaskclaw/amber)；考题本体私有。

## 发布纪律（红线）

1. 只发：分数与聚合、token 用量（若渠道上报）、速度、定性裁决。
2. 永不发：题目内容、oracle/判分器、transcript、考生工作区、任何能复原题面的中间产物。
3. 每期必钉：模型 ID、effort 档（思考力度档位）、日期（UTC）、harness 版本、每案内容哈希（bundle_sha，每题内容的哈希指纹）。哈希用于对照 [amber](https://github.com/getaskclaw/amber) 的公开哈希清单，自证题集未变。
4. 案号与题目结构属私有面：公开结果里案例只用稳定别名（A-xxxxxxxx，哈希派生）+ bundle 哈希作句柄；内部案号、变体名、题目描述永不出现。
5. 基调：这是社区实测，不是对厂商的攻击。数据说话，措辞克制。

## 一个方法论前提

同名模型、同 provider，两次跑也可能不同分——推理参数、负载、服务端版本都在漂；转发/聚合道还隔着一层上游路由，同名不一定是同一个端点。所以这里的一切结论都带日期与档位，且定期重测。单日数字是快照，不是定律。

## 最新成绩 / Results index

成绩速读：「格」= 榜单里的一个计分格；「invalid」= 这场考试作废（多为考场侧问题），不计能力分；「挂起」= 暂不定论、待复核或重考；「案级计数」= 以案为单位汇总的成绩数（一道题可能有多卷）；「三连考」= 一期连着考三条模型线；「腿」= 其中一条模型线；「车道冻结期」= 该渠道暂停补考的一段时间；「防御钉」= 防御类钉子题（刻意埋陷阱、专考模型犯错方式的难题）；「五档天梯」= 同一模型在 5 个 effort 档上的成绩阶梯；「GA 当日」= 模型正式发布当天。

| 期 | 内容 | 结论 |
|---|---|---|
| [2026-W39](results/2026-W39.md)（[EN](results/2026-W39.en.md)） | CommandCode 三连考：grok-4.7 / mimo-v2.6-pro / mimo-v2.6-flash；09-24 加餐 stealth/space-bunny-alpha | mimo-v2.6-pro **17/24**（1 invalid）；mimo-v2.6-flash **13/24**（6 负；5 案 invalid 不定模型罪）；grok-4.7 未完赛，7 案挂起待 09-29 原道重考；加餐 space-bunny-alpha **15/24**（stealth 免费窗，页内同端点并排） |
| [2026-W38 更正特刊](results/2026-W38-correction.md)（[EN](results/2026-W38-correction.en.md)） | W38 全库复核：本仓 0 个计分格改判 · 14 个计分格挂起；另附三连考 mimo 两个模型成绩入档 | W37 五档天梯 14 卷挂起（high 档 2 格 + 案级计数），车道冻结期内不补考；加餐：mimo-v2.6-pro 判过 17 / 判负 6 / 挂起 1，mimo-v2.6-flash 判过 13 / 判负 6 / 挂起 5（A-be92627f 同一案在两个模型因不同原因失败，分别记账） |
| [2026-W37](results/2026-W37.md) | deepseek/deepseek-v4.1-flash 全库首考（23 案，GA 当日） | **17/23**；UI 搭建卷满分（第五个公开通过该案的成绩）；防御钉 8/9 刷新全员纪录；同名跨厂商三家核对，确认都是真 v4.1；审查/视觉面是弱项 |

## 免责

与 CommandCode、DeepSeek（深度求索）无任何隶属/赞助关系。分数是特定周、特定档位的快照，不构成采购建议。
