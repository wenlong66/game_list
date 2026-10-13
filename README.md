# 开源游戏库：AI 换皮与持续开发选型

基于现有游戏保留主要玩法，替换游戏名、品牌、界面、美术和其他外部内容，制作自己的独立版本；优先选择能由 AI 编程完成资源接入、工程修改，并继续迭代玩法的项目。

分类更新：**2026-10-13**。原始收藏清单日期：2026-07-01。

> 平台硬条件：**支持 Windows，或同时支持 iOS + Android**。仅 Android 不满足。这里的 AI 指开发阶段的编程 Agent，不要求游戏运行时接入大模型。
>
> 当前分类是基于仓库说明、工程配置、许可证和官方文档的选型判断，**所有项目均未在本次实际构建、换皮或运行验收**。平台声明、已有构建工程与实测通过是三个不同状态；许可证摘要不替代完整的代码、素材和分发审计。

## 快速选择

| 目标 | 优先项目 | 使用边界 |
| --- | --- | --- |
| 先让 AI 完成一款 Windows 游戏的换皮 | **Unciv → Mindustry → Endless Sky** | 先保持二维表现与主要玩法，再处理品牌、资源和必要源码 |
| 现有收藏中希望覆盖 Windows、iOS、Android | **Mindustry** | 已有三端基础；必须实际验证 iOS 工具链、签名与分发条件 |
| 允许补充一个小型 Roguelike | **Shattered Pixel Dungeon** | 新增的上游候选，不是原版 pixel-dungeon，也没有自动创建 fork |
| 只做 Godot 小型沙盒原型 | **Microverse** | 开源部分是早期 Demo，不按成熟完整游戏评估 |

详见：[逐项分析、资料来源与换皮验收流程](docs/ai-game-dev-recommendations.md)。

## 分类标准

排序首先看 **AI 换皮接入成本**，其次看后续 AI 开发成本；同时检查平台路线、玩法完整度、资源依赖和授权限制。不仅按语言、项目大小、Star 数或“支持 Mod”判断。

- **A｜优先验证**：资源与规则入口清楚，适合先做独立换皮版本。
- **B｜有条件推荐**：能用，但要限制项目规模、动画复杂度或接受补玩法。
- **C｜低优先级**：不是不能改，而是整套资源替换、独立化或回归成本偏高。
- **D｜独立发行前置条件未解决**：授权限制或工程不完整，不能默认作为自由发行底座；不代表所有个人、非商业或已授权用途都不可用。
- **P｜平台待补**：当前收藏仓库尚未确认满足平台硬条件。

## A｜优先验证：3 个

| 项目 | 平台路线（非本次实测） | AI 换皮 / 后续开发 | 适合保留与替换的部分 | 主要条件 |
| --- | --- | --- | --- | --- |
| [Unciv](https://github.com/wenlong66/Unciv) | Windows、Android；官方未计划 iOS | 高 / 高 | 保留六边形回合制与规则；替换地形、文明主题、单位、建筑图标、UI 与文案 | MPL-2.0；UI skin 不是全界面覆盖，仍需部分源码修改 |
| [Mindustry](https://github.com/wenlong66/Mindustry) | Windows、Android、iOS；收藏版含 iOS 工程 | 高 / 高 | 保留生产链与塔防；替换建筑、炮塔、单位、地形、UI、音效和世界观 | GPL-3.0；完整资源规模不小；iOS 涉及 RoboVM、Arc、macOS 与签名 |
| [Endless Sky](https://github.com/wenlong66/endless-sky) | Windows；不把移动端计作已确认路线 | 高 / 中高 | 保留飞行、贸易、战斗；替换舰船、星球、阵营、UI 与剧情 | GPL-3.0；舰船图像影响碰撞轮廓，需校验武器和引擎挂点 |

## B｜有条件推荐：3 个

| 项目 | 平台路线（非本次实测） | 适合的换皮方式 | 没有列入 A 类的原因 |
| --- | --- | --- | --- |
| [Microverse](https://github.com/wenlong66/Microverse) | Windows；README 声明 Android；iOS 未确认 | Godot 小型沙盒、场景和角色替换、GDScript 迭代 | MIT 代码；公开的是 2025 年 6 月初版 Demo，玩法完整度和素材授权需单独验证 |
| [OpenRA](https://github.com/wenlong66/OpenRA) | Windows；优先按桌面独立游戏开发 | 用 Mod SDK 接入原创单位、建筑、地形，再打包独立版本 | GPL-3.0；多方向动画、建造与损坏状态增加美术成本；不能直接捆绑商业原作素材 |
| [Wesnoth](https://github.com/wenlong66/wesnoth) | Windows；不合并不同版本手机移植的能力 | 保留战棋规则，优先棋子化、少帧动画和原创战役 | GPL-2.0-or-later；全量替换并保持原版丰富动画时，美术工作量较高 |

## C｜低优先级：4 个

| 项目 | 平台 | 可以做什么 | 主要成本与风险 |
| --- | --- | --- | --- |
| [Cataclysm-DDA](https://github.com/wenlong66/Cataclysm-DDA) | Windows | JSON、tileset、物品与场景替换 | 物品、穿戴覆盖、车辆、地形等映射量大；按 CC BY-SA 3.0 与例外文件处理授权 |
| [OpenTTD](https://github.com/wenlong66/OpenTTD) | Windows | 自由资源、NewGRF、经营规则扩展 | 局部车辆换图不等于完整换皮；基础地形、道路、建筑、UI、方向与组合状态都要覆盖。可使用自由资源方案，不强制依赖原版素材 |
| [OpenRCT2](https://github.com/wenlong66/OpenRCT2) | Windows | 公园主题与资源改造 | 收藏版仍要求 RCT2 原版文件；必须验证原创替代资源和加载链完整，不能只换可见贴图 |
| [OpenXcom](https://github.com/wenlong66/OpenXcom) | Windows | 战棋规则、装备和资源改造 | 收藏版要求原版 X-COM 资源；完整独立化涉及旧格式、资源加载和构建依赖 |

## D｜独立发行前置条件未解决：3 个

| 项目 | 平台判断 | 主要障碍 | 可保留的用途 |
| --- | --- | --- | --- |
| [jynew](https://github.com/wenlong66/jynew) | 平台不是当前主要障碍 | 自定义许可证限制代码与资源，禁止未授权商业行为；换美术不能消除代码限制 | 授权范围内的社区 Mod、学习或获得额外授权后重新评估 |
| [DevilutionX](https://github.com/wenlong66/DevilutionX) | Windows，另有移动工程；未实测 | 收藏版 Sustainable Use License 对外分发有免费、非商业限制，另涉及 Diablo 数据 | 许可范围内的非商业改造与引擎研究 |
| [CnC_Remastered_Collection](https://github.com/wenlong66/CnC_Remastered_Collection) | Windows | 主要是两个游戏 DLL 和地图编辑器；不是完整独立游戏，使用编译结果需拥有重制版 | 专用 Mod 与历史 RTS 源码研究 |

没有默认要求商业化或闭源。D 类表示需要先澄清授权或补全工程，**不等同于“AI 不能修改”**。

## P｜平台待补：1 个

| 项目 | 当前确认范围 | 处理方式 |
| --- | --- | --- |
| [pixel-dungeon（原版）](https://github.com/wenlong66/pixel-dungeon) | 收藏仓库只确认 Android 工程，另需 PD-classes；未确认 Windows 或 iOS+Android 路线 | 暂不计入合格池。不要把其他同名版本或衍生项目的平台能力填到这个条目 |

## 补充候选｜不混入原有 14 个

| 项目 | 平台基础 | 推荐定位 | 注意事项 |
| --- | --- | --- | --- |
| [Shattered Pixel Dungeon](https://github.com/00-Evan/shattered-pixel-dungeon) | 上游有 Desktop、Android、iOS 工程 | **A 类补充候选**：小型 Roguelike 换皮与持续开发 | GPL-3.0；有自有版本修改指南；iOS 工具链与签名仍需验证。本次只记录上游，不创建 fork |

## 游戏开发相关仓库｜4 个工具，单独分类

| 项目 | 正确定位 | 对本目标的价值与限制 |
| --- | --- | --- |
| [EGamePlay](https://github.com/wenlong66/EGamePlay) | 战斗 / 技能框架 | 可用于后续开发，不是完整游戏；README 列有收费插件和移植冲突提示 |
| [spine2d-animation-mcp](https://github.com/wenlong66/spine2d-animation-mcp) | 实验性资产管线 | 当前为 PSD → Spine 骨架 / 图集概念验证，**尚无动画生成**；真实素材与编辑器验证仍是待办 |
| [AssetStudio](https://github.com/wenlong66/AssetStudio) | Unity 资源查看 / 提取工具 | 不提供游戏底座；能够导出不代表取得素材使用权 |
| [skynet](https://github.com/wenlong66/skynet) | 游戏服务端框架 | 可让 AI 开发服务器业务；不解决客户端换皮与客户端平台适配 |

## 外围项目｜保留，不参加游戏底座排名

| 项目 | 原清单定位 |
| --- | --- |
| [MisakaTranslator](https://github.com/wenlong66/MisakaTranslator) | Galgame / 文字游戏翻译工具 |
| [Sunshine](https://github.com/wenlong66/Sunshine) | 游戏串流服务端 |
| [remotion](https://github.com/wenlong66/remotion) | React 编程式视频生成工具 |
| [AIAssistOpenCV](https://github.com/wenlong66/AIAssistOpenCV) | AI 游戏辅助工具 |
| [MiroFish](https://github.com/wenlong66/MiroFish) | 群体智能引擎，非本清单中的完整游戏底座 |

## 换皮与发行的共通边界

**换皮是产品选择，不会自动消除代码许可义务。**保留应保留的许可证、版权声明和署名；源码许可与素材许可分开核验。GPL 不等于禁止收费，MPL 不等于整套代码可闭源，MIT 代码也不代表第三方素材可随意使用。

**平台工程存在不等于当前可构建，更不等于商店审核通过。**iOS 签名、工具链、许可证与具体分发方式，以及 App Store 的 Copycats / Spam 规则都需要独立检查。

**编程接入不等于美术生产。**AI 可承担资源清单、切图、打包、引用映射、界面与代码修改；一致的美术、动画、音频需要授权素材或生成工具供给，并做视觉验收。

## 开工前验收

先固定版本并构建原版，再完成一个可玩闭环的完整换皮；验证资源无错误回退、碰撞与动画正常、独立包名和存档空间正确、目标设备能够运行。随后再增加玩法。内部玩法 ID 不做无理由的全局替换，避免破坏引用和存档。

具体清单与授权来源见[详细分析](docs/ai-game-dev-recommendations.md)。上述验收尚未执行，不以“文档已分类”代表“游戏已验证可发行”。

## 原始记录与维护

原有 **14 个游戏、4 个开发工具和5 个外围项目均保留**；Shattered Pixel Dungeon 为额外候选，不冒充原有收藏。

原 README（包括原仓库日期、语言和描述）完整保存在[原始收藏快照](docs/archive/original-catalog-2026-07-01.md)，其旧描述不作为当前推荐依据。分类调整原因及资料见[详细文档](docs/ai-game-dev-recommendations.md)。

本次只更新分类文档和维护规则，**没有刷新或改写** [仓库元数据缓存](wenlong66_repos_updated.json)，也没有修改任何游戏本体、创建游戏 fork 或部署游戏。
