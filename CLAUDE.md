# CLAUDE.md

本项目用于记录和筛选高质量开源游戏仓库。

## 项目目标

- 从 GitHub 用户 [`wenlong66`](https://github.com/wenlong66?tab=repositories) 的公开仓库中筛选游戏相关项目。
- 优先记录游戏本体、游戏引擎、游戏开发框架、游戏服务端框架和游戏资源工具。
- 将筛选结果维护在 [README.md](README.md)。

## 当前数据来源

使用 GitHub API 按最近更新时间分页获取公开仓库，合并后只写入一个缓存文件 [wenlong66_repos_updated.json](wenlong66_repos_updated.json)：

```text
https://api.github.com/users/wenlong66/repos?per_page=150&page=1&sort=updated&direction=desc
```

当前目标数量为 150 个；实际公开仓库返回 113 个。分页结果不单独落盘，只更新合并缓存。

本地缓存文件：

- [wenlong66_repos_updated.json](wenlong66_repos_updated.json)：唯一保留的 GitHub API 原始仓库数据缓存。
- 后续更新只更新 [wenlong66_repos_updated.json](wenlong66_repos_updated.json)，不再保留分页缓存文件。

## 筛选规则

### 放入“最近更新的游戏仓库”

满足以下任一条件：

- 仓库本身是可玩的开源游戏。
- 仓库是经典游戏重实现、克隆或重制源码。
- 仓库是明确的游戏引擎，并直接服务于可玩游戏。
- 仓库描述明确包含游戏类型，例如 RTS、RPG、Roguelike、生存、模拟经营、塔防等。

### 放入“游戏开发相关仓库”

满足以下任一条件：

- 游戏开发工具。
- 游戏服务端框架。
- 游戏战斗、技能、UI、资源处理框架或工具。
- 与 Cocos、Unity、Godot、skynet、SPINE2D 等游戏开发生态直接相关。

### 放入“暂不归类为游戏仓库”

满足以下任一条件：

- 名称或描述包含游戏相关词，但不是游戏本体或开发基础设施。
- 游戏辅助、游戏串流、翻译器、AI 工作流、资料工具等边缘项目。
- 关键字误命中，例如 `framework`、`engine`、`skills` 等，但实际不是游戏相关。

## 排除规则

- 不因为仓库描述里出现 `framework`、`engine`、`server` 就自动归类为游戏项目。
- 不把通用 AI agent、Claude Code 插件、网络代理、音乐服务等放入游戏列表。
- 不删除用户手动整理过的 README 内容，除非用户明确要求重建。
- 不删除临时 JSON 文件，除非用户明确要求清理。

## 更新流程

1. 获取最近更新仓库数据。
2. 合并分页结果到 [wenlong66_repos_updated.json](wenlong66_repos_updated.json)。
3. 按筛选规则找出候选仓库。
4. 人工判断误命中，避免只靠关键字。
5. 更新 [README.md](README.md) 中对应分类。
6. 保留不确定项说明，方便后续复查。

## 当前记录状态

截至 2026-06-30：

- 已按最近更新时间查询公开仓库。
- 目标 150 个，实际返回 113 个。
- [README.md](README.md) 已记录主要游戏仓库、游戏开发相关仓库、暂不归类仓库。
