# AI 编程快速开发游戏仓库推荐

本文记录哪些游戏仓库更适合用 AI 编程快速扩展玩法、内容或原型。

## 推荐仓库

| 推荐级别 | 仓库 | 适合方向 | 原因 |
| --- | --- | --- | --- |
| 首选 | [Microverse](https://github.com/wenlong66/Microverse) | AI 沙盒 Demo、多智能体模拟、NPC 行为、事件系统 | Godot 4 项目，适合快速做小型可玩原型。 |
| 首选 | [jynew](https://github.com/wenlong66/jynew) | RPG 剧情、任务、技能、道具、NPC 对话 | 已有 RPG 框架和可玩样例，适合 AI 生成内容和配置。 |
| 推荐 | [Mindustry](https://github.com/wenlong66/Mindustry) | Mod、新方块、新单位、地图机制、平衡调整 | Java 项目成熟，适合局部扩展，但整体项目较大。 |
| 推荐 | [pixel-dungeon](https://github.com/wenlong66/pixel-dungeon) | Roguelike 职业、怪物、装备、地牢事件 | 规则清晰，适合做小范围玩法改造。 |
| 推荐 | [OpenRA](https://github.com/wenlong66/OpenRA) | RTS Mod、新单位、新阵营、规则调整 | 数据驱动强，适合内容扩展；不建议先改引擎核心。 |

## 不优先作为快速开发起点

这些项目更大、更老或更偏底层，适合研究和长期维护，不适合快速起步：

- [OpenRCT2](https://github.com/wenlong66/OpenRCT2)：大型 C++ 模拟经营游戏重实现，系统复杂。
- [wesnoth](https://github.com/wenlong66/wesnoth)：大型 C++ 回合制策略游戏，内容多但上手慢。
- [OpenTTD](https://github.com/wenlong66/OpenTTD)：大型 C++ 交通运输模拟游戏，规则深。
- [Cataclysm-DDA](https://github.com/wenlong66/Cataclysm-DDA)：超大型 C++ / JSON 生存 Roguelike，内容扩展可以，核心开发慢。
- [CnC_Remastered_Collection](https://github.com/wenlong66/CnC_Remastered_Collection)：老代码 / 重制源码，快速 AI 开发不优。
- [OpenXcom](https://github.com/wenlong66/OpenXcom)：C++ 战术策略重实现，适合研究，不适合快改。
- [endless-sky](https://github.com/wenlong66/endless-sky)：内容驱动潜力不错，但需要先确认数据格式和构建难度。

## 结论

- 想用 AI 做新游戏原型：优先选 **Microverse**。
- 想用 AI 扩展已有 RPG 内容：优先选 **jynew**。
- 想做可发布 Mod：优先选 **Mindustry** 或 **OpenRA**。
- 想做小型 Roguelike 玩法改造：选 **pixel-dungeon**。
