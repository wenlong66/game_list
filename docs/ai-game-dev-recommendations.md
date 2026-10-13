# game_list：AI 换皮、持续开发与平台适配分类

整理日期：2026-10-13。

本版依据已明确的“独立换皮 + AI 持续开发 + 平台门槛”目标，替代原有仅侧重 Mod / 快速原型的推荐。返回[分类首页](../README.md)；原始收藏记录见[历史快照](archive/original-catalog-2026-07-01.md)。

## 目标与边界

目标是基于现有项目制作独立版本：保留主要玩法，替换游戏名、品牌、界面、美术和其他需要替换的内容，由 AI 编程承担资源接入、工程修改和后续迭代。

平台条件严格按 **Windows，或同时支持 iOS + Android** 理解；仅 Android 不满足。没有把“引擎理论可导出”计作“该项目已经支持”，也没有把同名游戏其他移植版本的能力算到当前收藏仓库。

用户没有要求闭源，因此 GPL 项目不会仅因需要提供相应源代码而被排除。收费发行限制另列。以下“高、中、低”均为工程选型判断，不是实测成功率；本次未编译运行、未实测 AI 换皮，未完成全量素材和依赖授权审计。

## 一、现有 14 个游戏的分类

| 分类 | 项目 | 平台判断 | AI 换皮与持续开发判断 | 主要限制 |
|---|---|---|---|---|
| A：优先 | Unciv | Windows、Android；官方未计划 iOS | 换皮高、后续开发高。地图 tileset、UI skin 和数据规则入口清楚，适合先维持二维表现再替换主题 | MPL-2.0；UI skin 不覆盖全部界面元素，图标、字体和布局仍可能需要源码层修改 |
| A：优先 | Mindustry | Windows、Android、iOS；收藏仓库含 iOS 工程 | 换皮高、后续开发高。已有图片覆盖、图集打包和内容扩展机制 | GPL-3.0；完整资源规模不小；iOS 构建涉及 RoboVM、Arc 原生库和签名，不能视为一键出包 |
| A：优先 | Endless Sky | Windows；本次不把移动端算作已验证路线 | 换皮高、后续开发中高。图片和数据分离，舰船主要使用可旋转的二维图像 | GPL-3.0；全量剧情与资源规模较大；舰船轮廓影响碰撞，武器与引擎挂点需要校验 |
| B：有条件 | Microverse | Windows；README 声明 Android；iOS 尚未确认为现成项目路线 | 小型原型的换皮和脚本开发友好 | MIT 代码，但开源内容是 2025 年 6 月初版 Demo；不是成熟完整游戏；素材授权独立核验 |
| B：有条件 | OpenRA | Windows；以桌面独立游戏为路线 | YAML、Lua、C# 与 Mod SDK 适合 AI 修改规则、接入原创素材并打包 | GPL-3.0；多方向动画、地形、建造/损坏状态等增加制作量；不应直接带上商业原作素材 |
| B：有条件 | Wesnoth | Windows；不把不同版本的手机移植计作现成三端工程 | WML/Lua 内容开发友好；小规模、棋子化或少帧风格的换皮更可控 | GPL-2.0-or-later；保持原版丰富动画表现并全量替换时，美术工作量高 |
| C：低优先 | Cataclysm-DDA | Windows，满足平台门槛 | JSON/tileset 接入可自动化，但完整换皮和持续跨系统改动成本偏高 | 物品、穿戴覆盖、车辆、地形等大量资源映射；需按 CC BY-SA 3.0 与例外文件处理授权 |
| C：低优先 | OpenTTD | Windows，满足平台门槛 | 可开发新资源与规则，但完整视觉重做成本高 | 不能把车辆 NewGRF 的局部换图等同于整个游戏换皮；基础地形、界面、方向与组合状态都要覆盖。存在自由资源方案，不必依赖原版素材 |
| C：低优先 | OpenRCT2 | Windows，满足平台门槛 | 可以改，但不优先作为低成本 AI 换皮项目 | 收藏版运行说明仍要求 RCT2 原版文件；必须完成替代资源和加载路径验证，而非只替换可见贴图 |
| C：低优先 | OpenXcom | Windows，满足平台门槛 | 可做规则与素材改造，但完整独立化成本偏高 | 收藏版要求原版 X-COM 资源；需要验证没有原版数据仍能完整运行，兼顾旧资源格式和构建依赖 |
| D：不进入默认独立发行候选 | jynew | 平台不是主要淘汰原因 | 技术上可以修改剧情、角色和界面 | 自定义许可证限制代码与资源使用，禁止未授权商业行为；换美术不会消除代码授权限制。授权范围内的免费社区 Mod 是另一条路线 |
| D：不进入默认独立发行候选 | DevilutionX | Windows，另有移动工程；平台不是主要淘汰原因 | 技术上可做 Mod 和引擎修改 | 收藏版采用 Sustainable Use License，对外分发有免费、非商业限制；还涉及原版 Diablo 数据。不是可自由收费换皮发行的底座 |
| D：不进入默认独立发行候选 | CnC_Remastered_Collection | Windows | 适合专用 Mod 和源码研究，不是现成独立游戏底座 | 主要是两个游戏 DLL 与地图编辑器，并非完整独立产品；使用编译结果需拥有重制版游戏；归档且构建较旧 |
| P：平台待补，不计入合格池 | pixel-dungeon（原版） | 收藏仓库只确认 Android 工程 | 小型 Roguelike 玩法和图集替换有价值 | 尚未从该仓库确认 Windows 或 iOS+Android 构建路线；不能用其他同名产品/分支的平台能力代替 |

## 二、优先项目应怎么使用

### Unciv：Windows / Android 换主题的第一验证对象

建议先维持六边形地图、二维图标和原有规则，替换文明主题、地形、单位、建筑图标、界面和文案。不要同时把二维画面改成自由镜头三维场景；那已经是渲染重构，不是换皮。

官方提供自定义 tileset 和 UI skin 文档，但 UI skin 明确不支持全部界面元素、图标和字体。最终独立版需要在资源层之外处理必要的代码、品牌、包名、存档位置和发行配置。

### Mindustry：现有清单里的三端优先对象

保留生产链、资源流转与塔防规则，先设计规模可控的原创主题和资源集。利用资源名、图集打包和内容配置完成替换，再按需修改 Java 逻辑。

iOS 工程真实存在，不过收藏版本的构建脚本还涉及 RoboVM、Arc 原生库、macOS 与签名。必须实测当前工具链，不能将“已有 iOS 工程”写成“换完立即能上架”。

### Endless Sky：低人物动画负担的 Windows 候选

舰船以二维图像旋转呈现，资源可以通过图片与文本配置接入，适合围绕太空或相近飞行题材做新主题。

注意其碰撞轮廓会依据图像生成。新图变胖、变长或出现杂散像素，会改变碰撞；武器和引擎挂点也要重新验证。不能以“图片能显示”作为换皮完成标准。

### Microverse：仅在小型沙盒目标下提高优先级

Godot/GDScript 与命令行导入、运行、导出能力对自动化友好。但这个仓库的公开内容是早期 Demo。只想做小型换皮原型时可以优先；需要拿现成成熟游戏换皮发行时不排在前三。

## 三、一个值得单独补充的替代项目

**[Shattered Pixel Dungeon](https://github.com/00-Evan/shattered-pixel-dungeon)**，不是现有收藏里的原版 pixel-dungeon。本次只补充上游链接和候选定位，没有创建 fork，也不计入原有 14 个项目。

上游明确提供 Android、iOS、Desktop 工程，并有制作自有版本的变更指南，覆盖游戏名、包名、图标、标题画面、存档身份、更新地址等。建议单独加入 A 类的“小型 Roguelike 候选”，不要直接把它的平台能力填到原版条目。

其代码为 GPL-3.0。iOS 文档也明确承认从零构建比 Android/桌面复杂，并不是完整的一键指南，因此仍须验证 RoboVM、签名、Xcode 和分发条件。

## 四、开发工具不与游戏本体混排

| 项目 | 分类 | 结论 |
|---|---|---|
| EGamePlay | 战斗/技能框架 | 可做后续开发模块；不是可直接换皮的完整游戏。README 列有收费插件及移植冲突提示 |
| spine2d-animation-mcp | 实验性资产管线 | 当前是 PSD 到 Spine 骨架/图集的概念验证，不是已经完成动画生成的成熟工具 |
| AssetStudio | 资源查看/提取工具 | 不提供游戏底座；能导出素材不代表拥有使用授权 |
| skynet | 服务端框架 | 可让 AI 开发服务器业务，但与客户端换皮和客户端平台支持是两回事 |

原清单的 MisakaTranslator、Sunshine、remotion、AIAssistOpenCV、MiroFish 继续保留为外围工具，不参与换皮游戏底座排名。

## 五、授权与上架边界

- 换皮是产品选择，不是所有开源许可证的统一要求。换了美术、游戏名，也必须保留应保留的许可证、版权声明和署名。
- Unciv 的 MPL-2.0 是文件级 copyleft：分发时需提供受 MPL 覆盖部分及其修改的源码。独立新文件且不包含 MPL 代码，可以适用其他条款；不是所有代码都能直接闭源。
- Mindustry、Endless Sky 等 GPL 项目可以收费分发，但需要按对应许可处理受覆盖衍生代码、相应源码和用户权利。商业化不等于闭源。
- Microverse 的 MIT 代码相对灵活；第三方素材、音频、字体、依赖仍分别审核。
- Jynew、DevilutionX 的限制不能靠换美术或让 AI 重写几段代码自动消除。
- iOS 技术支持不等于 App Store 审核通过。Apple 的 4.1 Copycats 与 4.3 Spam 规则需要独立评估，不能承诺换图即可上架；GPL/第三方许可与具体分发方式也需核验。

## 六、建议的首次验收流程

这是建议流程，不是已完成工作。

1. 固定上游版本，构建未修改版本，记录依赖、资源授权与运行入口。
2. 建立外观资源清单：图片、图集、方向帧、动画状态、字体、音频、界面和资源回退路径。
3. 完成一个最小闭环的全套换皮，而非只换标题：一个可玩的关卡/对局或战斗循环，包含角色/单位、场景、界面、音效和反馈。
4. 编程 Agent 负责切图、打包、映射、配置、导入和代码修改；美术由授权素材或图像生成工具供给，并进行视觉验收。不能把“会写代码”当作自动拥有稳定的全量美术产能。
5. 验证新版本不误用旧图和旧服务，保留必要署名；使用独立包名、存档空间及更新配置。内部玩法 ID 不做无理由的全局替换，以减少存档和引用破坏。
6. 测试换皮后的碰撞、点击区域、图层、动画、文本布局、保存/加载和目标设备性能；随后再做玩法迭代。

## 七、最终选择

- **Windows 优先**：Unciv → Mindustry → Endless Sky。
- **现有清单里要求 Windows+iOS+Android**：先验证 Mindustry。
- **允许补充一个小型 Roguelike**：加入 Shattered Pixel Dungeon，替代原版 pixel-dungeon 作为新项目候选。
- **只做 Godot 小型原型**：Microverse；不要把早期 Demo 当作成熟游戏成品。

## 八、为什么调整旧推荐

原推荐主要回答“适合 AI 快速做 Mod 或原型吗”；本版回答“适合保留玩法、全套换美术和包装，再维护独立游戏吗”。因此：

- Unciv、Mindustry、Endless Sky 提升为优先验证对象；不是承诺已经换皮成功。
- Microverse 从通用首选改为小型沙盒条件推荐，避免把早期 Demo 当作成熟游戏。
- jynew 的代码与资源授权成为独立发行前置条件，不能靠换图绕过。
- 原版 pixel-dungeon 单列平台待补，Shattered Pixel Dungeon 作为不同项目补充。
- Wesnoth、OpenRA、Cataclysm-DDA 等的内容扩展能力仍有价值，但与完整视觉替换的工作量分开评估。

本次只做文档更新，不刷新仓库元数据缓存，也不改任何游戏工程。后续应逐项记录固定提交、构建命令、测试平台、资源清单和实际验收结果，再调整分类。

## 资料来源

以下来源包含用户收藏仓库和上游官方文档。默认分支与在线文档会变化，实施时应固定提交或版本。

1. [game_list README](https://github.com/wenlong66/game_list/blob/main/README.md)
2. [Unciv 收藏版许可证](https://github.com/wenlong66/Unciv/blob/master/LICENSE)
3. [Unciv 平台说明](https://github.com/yairm210/Unciv)
4. [Unciv 自定义 tileset](https://yairm210.github.io/Unciv/Modders/Creating-a-custom-tileset/)
5. [Unciv UI skin 及其限制](https://yairm210.github.io/Unciv/Modders/Creating-a-UI-skin/)
6. [Mozilla MPL 2.0 FAQ](https://www.mozilla.org/en-US/MPL/2.0/FAQ/)
7. [Mindustry 官方平台入口](https://mindustrygame.github.io/)
8. [Mindustry 收藏版 GPL 许可证](https://github.com/wenlong66/Mindustry/blob/master/LICENSE)
9. [Mindustry 收藏版 iOS 构建脚本](https://github.com/wenlong66/Mindustry/blob/master/ios/build.gradle)
10. [Mindustry Mod 资源与覆盖机制](https://mindustrygame.github.io/wiki/modding/1-modding/)
11. [Endless Sky 收藏版 README](https://github.com/wenlong66/endless-sky/blob/master/README.md)
12. [Endless Sky 插件、图片与数据](https://github.com/endless-sky/endless-sky/wiki/CreatingPlugins)
13. [Endless Sky 舰船图像与碰撞](https://github.com/endless-sky/endless-sky/wiki/CreatingShips)
14. [Microverse 收藏版 README](https://github.com/wenlong66/Microverse/blob/main/README.md)
15. [Microverse 实际工程配置](https://github.com/wenlong66/Microverse/blob/main/project.godot)
16. [Godot 命令行运行与导出](https://docs.godotengine.org/en/stable/tutorials/editor/command_line_tutorial.html)
17. [Godot iOS 导出条件](https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_ios.html)
18. [OpenRA Mod SDK 独立打包及代码/资产授权区分](https://github.com/OpenRA/OpenRAModSDK)
19. [OpenRA sprite sequences](https://docs.openra.net/en/release/sprite-sequences/)
20. [Wesnoth 动画配置](https://wiki.wesnoth.org/AnimationWML)
21. [Wesnoth 收藏版 README](https://github.com/wenlong66/wesnoth/blob/master/README.md)
22. [Cataclysm-DDA tileset 文档](https://docs.cataclysmdda.org/TILESET.html)
23. [Cataclysm-DDA 收藏版 README](https://github.com/wenlong66/Cataclysm-DDA/blob/master/README.md)
24. [OpenTTD 自由资源与平台说明](https://github.com/wenlong66/OpenTTD/blob/master/README.md)
25. [OpenTTD NewGRF](https://wiki.openttd.org/en/Development/NewGRF/Main%20Page)
26. [OpenRCT2 原版文件要求](https://github.com/wenlong66/OpenRCT2/blob/develop/readme.md)
27. [OpenXcom 原版资源要求](https://github.com/wenlong66/OpenXcom/blob/master/README.md)
28. [Jynew 许可证](https://github.com/wenlong66/jynew/blob/main/LICENSE)
29. [DevilutionX 收藏版许可证](https://github.com/wenlong66/DevilutionX/blob/master/LICENSE.md)
30. [CnC Remastered 收藏版说明](https://github.com/wenlong66/CnC_Remastered_Collection/blob/master/README.md)
31. [原版 pixel-dungeon 工程](https://github.com/wenlong66/pixel-dungeon)
32. [Shattered Pixel Dungeon 工程与平台](https://github.com/00-Evan/shattered-pixel-dungeon)
33. [Shattered 自有版本变更指南](https://github.com/00-Evan/shattered-pixel-dungeon/blob/master/docs/recommended-changes.md)
34. [Shattered iOS 构建说明及困难](https://github.com/00-Evan/shattered-pixel-dungeon/blob/master/docs/getting-started-ios.md)
35. [GNU GPL FAQ](https://www.gnu.org/licenses/gpl-faq.en.html)
36. [Apple App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
37. [EGamePlay 收藏版 README](https://github.com/wenlong66/EGamePlay/blob/main/README.md)
38. [spine2d-animation-mcp 收藏版现状](https://github.com/wenlong66/spine2d-animation-mcp/blob/main/README.md)
39. [AssetStudio 收藏版 README](https://github.com/wenlong66/AssetStudio/blob/master/README.md)
40. [skynet 收藏版 README](https://github.com/wenlong66/skynet/blob/master/README.md)
