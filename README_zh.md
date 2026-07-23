# Billboards-Remake

[English](README.md) | **中文**

基于 [MrXiaoM/Billboards](https://github.com/MrXiaoM/Billboards) 的 Minecraft 广告牌插件重制版，适配 **1.21.1 Purpur/Paper**。

## 与原版的区别 (Fork Changes)

| 变更项 | 原版 | 本版 |
|--------|------|------|
| Minecraft 版本 | 1.20.4 | **1.21.1** |
| 服务端 API | Spigot API 1.20.4 | **Paper API 1.21.1** |
| ProtocolLib | 5.2.0 | **5.3.0** |
| 构建系统 | Gradle (Kotlin DSL) | **Maven** |
| Java 目标版本 | 1.8 | **21** |
| 构建脚本语言 | Kotlin DSL | **Maven POM** |
| 插件名称 | Billboards | **Billboards-Remake** |
| 作者 | blablubbabc, MrXiaoM | blablubbabc, MrXiaoM, **baqiwenye** |

### API 适配

- **`Material.data` 修复** — 1.21 移除了 `Material.data` 字段，改用 `Tag.ALL_SIGNS` 判断告示牌类型
- **`Enchantment.DURABILITY` 修复** — 1.21 移除了该字段，改用 `Enchantment.UNBREAKING`
- **`Block.getData()` 清理** — 移除 1.21 中已废弃的旧版 API 调用

---

## 插件介绍

Billboards 允许你设置可租用的告示牌。例如在受保护的重生点区域放置一面广告牌墙，玩家即使没有建筑权限也能租用并编辑这些告示牌。

## 功能

- 使用 **ProtocolLib** 发送告示牌编辑界面，无需手持告示牌编辑
- 支持格式化代码（`&` → `§`），含权限控制
- `/billboard reload` 重载配置和语言文件
- 告示牌编辑 GUI 菜单
- 告示牌点击操作（如传送至领地）
- **Folia 兼容**

## 指令

- `/billboard [<价格> <天数>] [创建者]` — 创建广告牌
- `/billboard reload` — 重载配置与语言

## 权限

| 权限节点 | 说明 | 默认值 |
|----------|------|--------|
| `billboards.admin` | 管理所有广告牌 | OP |
| `billboards.rent` | 租用并编辑广告牌 | true |
| `billboards.create` | 创建玩家广告牌（实验性） | false |
| `billboards.sign.color` | 在告示牌上使用颜色代码 | OP |
| `billboards.sign.format` | 在告示牌上使用格式代码 | OP |
| `billboards.sign.format.magic` | 使用 §k 魔法代码 | OP |

## 前置插件

- **Vault** — 经济交互
- **ProtocolLib** — 告示牌编辑界面
- **PlaceholderAPI** (可选) — 支持 PAPI 变量

## 构建

```bash
./mvnw clean package
```

构建产物位于 `target/Billboards-Remake-2.4.0.jar`。

## 配置

| 配置项 | 默认值 | 说明 |
|--------|--------|------|
| `default-price` | 10 | 租用广告牌的默认价格 |
| `default-duration-in-days` | 7 | 默认租用天数 |
| `max-billboards-per-player` | -1 | 玩家同时租用上限（-1 无限制） |

所有消息均可通过 `plugins/Billboards-Remake/messages.yml` 自定义。

## 鸣谢

- 原作者：[blablubbabc](https://dev.bukkit.org/projects/billboards/)
- 1.20.4 重制：[MrXiaoM](https://github.com/MrXiaoM/Billboards)
- 1.21.1 适配：[DobeShadow](https://github.com/DobeShadow/Billboards-Remake)
