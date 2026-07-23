# Billboards-Remake

**English** | [中文](README_zh.md)

A fork of [MrXiaoM/Billboards](https://github.com/MrXiaoM/Billboards), updated and remastered for **Minecraft 1.21.1 Purpur/Paper**.

## Fork Changes

| Item | Original | This Fork |
|------|----------|-----------|
| Minecraft Version | 1.20.4 | **1.21.1** |
| Server API | Spigot API 1.20.4 | **Paper API 1.21.1** |
| ProtocolLib | 5.2.0 | **5.3.0** |
| Build System | Gradle (Kotlin DSL) | **Maven** |
| Java Target | 1.8 | **21** |
| Plugin Name | Billboards | **Billboards-Remake** |
| Authors | blablubbabc, MrXiaoM | blablubbabc, MrXiaoM, **baqiwenye** |

### API Fixes for 1.21.1

- **`Material.data` removal** — 1.21 removed `Material.data` field. Now uses `Tag.ALL_SIGNS` to detect sign blocks.
- **`Enchantment.DURABILITY` removal** — Replaced with `Enchantment.UNBREAKING`.
- **`Block.getData()` removal** — Cleaned up deprecated pre-1.13 API calls.

---

Billboards gives you the possibility to setup rentable signs. You could for example place a wall of those signs at your protected spawn region and players will be able to rent those signs and edit their text, even though they have no build permission there.

## Features

- **ProtocolLib-powered** sign editing GUI — no need to hold a sign to edit
- Format code support (`&` → `§`) with permissions
- `/billboard reload` to hot-reload config and messages
- Sign edit GUI menu
- Sign click actions (e.g. teleport to a region via command)
- **Folia-compatible**

## Commands

- `/billboard [<price> <duration>] [creator]` — Create a billboard sign
- `/billboard reload` — Reload configuration and messages

Aliases: `billboards`, `adsign`

## Permissions

| Permission | Description | Default |
|------------|-------------|---------|
| `billboards.admin` | Manage all billboard signs | OP |
| `billboards.rent` | Rent and edit billboard signs | true |
| `billboards.create` | Create player billboard signs (experimental) | false |
| `billboards.sign.color` | Use color codes on signs | OP |
| `billboards.sign.format` | Use format codes on signs | OP |
| `billboards.sign.format.magic` | Use §k magic code on signs | OP |

## Dependencies

- **Vault** — Economy
- **ProtocolLib** — Sign editor GUI
- **PlaceholderAPI** *(optional)* — PAPI placeholders

## Building

```bash
./mvnw clean package
```

Output: `target/Billboards-Remake-2.4.0.jar`

## Configuration

| Setting | Default | Description |
|---------|---------|-------------|
| `default-price` | 10 | Default rent price |
| `default-duration-in-days` | 7 | Default rent duration |
| `max-billboards-per-player` | -1 | Max signs a player can rent simultaneously (-1 = unlimited) |

All messages are customizable via `plugins/Billboards-Remake/messages.yml`.

## Credits

- Original author: [blablubbabc](https://dev.bukkit.org/projects/billboards/)
- 1.20.4 remaster: [MrXiaoM](https://github.com/MrXiaoM/Billboards)
- 1.21.1 update: [DobeShadow](https://github.com/DobeShadow/Billboards-Remake)
