# 🛰️ ACL4SSR 自用定制版

> 基于 [zsokami/ACL4SSR](https://github.com/zsokami/ACL4SSR) 修改的自用配置，适配 **Surge / Clash / Clash Meta (Mihomo)** 等订阅转换工具。

---

## 📦 配置文件

### 🗺️ Full 版（含地区分组）

| 版本 | 特点 | 配置链接 |
| --- | --- | --- |
| 🛡️ 无 DNS 泄漏 | 带 `no-resolve` 防护 | https://raw.githubusercontent.com/EvilNeko/ACL4SSR/main/ACL4SSR_Online_Full_Mannix_No_DNS_Leak.ini |
| ⚡ 常规版 | 去除 `no-resolve` | https://raw.githubusercontent.com/EvilNeko/ACL4SSR/main/ACL4SSR_Online_Full_Mannix.ini |

### 🪶 精简版（去除地区分组，仅保留核心策略组）

| 版本 | 特点 | 配置链接 |
| --- | --- | --- |
| 🛡️ 无 DNS 泄漏 | 带 `no-resolve` 防护 | https://raw.githubusercontent.com/EvilNeko/ACL4SSR/main/ACL4SSR_Online_Mannix_No_DNS_Leak.ini |
| ⚡ 常规版 | 去除 `no-resolve` | https://raw.githubusercontent.com/EvilNeko/ACL4SSR/main/ACL4SSR_Online_Mannix.ini |

---

## 🧭 分组结构

### ✈️ 选择节点 · 总顺序

```
选择节点 → 低延迟 → 指定 → 中国 → 香港 → 美国 → 英国 → 新加坡 → 日本 → 其他
→ 手动指定组（👆🏻 同序）→ 墙内 / 广告 / B站 / AI / 未知站点
```

### 🔧 分组改动

- ✏️ **改名**：`✈️ 起飞` → `✈️ 选择节点`（ruleset 引用同步更新）
- 🗑️ **去除**：`🇹🇼 台湾` / `👆🏻🇹🇼 台湾`
- ➕ **新增**：`🇬🇧 英国` / `👆🏻🇬🇧 英国`
- 🖐️ 手动指定组（`👆🏻` 前缀）的变更与顺序同理

### ⚡ 自动测速

- `⚡ 低延迟` 为 `✈️ 选择节点` 的**默认首选**策略，自动测速已启用
- 测速地址：`https://i.ytimg.com/generate_204`

---

## 🐛 最近修复记录

- **🇬🇧 英国节点误入「其他」组**：`🎏 其他` / `👆🏻🎏 其他` 的排除列表未包含 `🇬🇧`，导致英国节点同时落入「英国」与「其他」两个组，现已将 `🇬🇧` 加入排除列表。
- **🇱🇦 洛杉矶节点被误判为老挝**：原规则将 `LA`（洛杉矶缩写）识别为老挝代码 `LAO?`，导致 `US-LA`、`LA-01` 等常见命名被错误标记为老挝旗标。现改为：
  - 老挝仅识别完整代码 `LAO`（及 `Lao` / `Vientiane` / 万象等关键词）
  - 美国规则加入 `LA` 作为洛杉矶匹配词（带边界断言，不影响 `La Paz` 等命名）

---

## ⚠️ 注意事项

> ⚠️ 每个组名的空格后面都添加了一个隐藏字符 `\u200d`，用于防止与节点重名，**改名需谨慎**。

---

## 🙏 致谢

- [ACL4SSR/ACL4SSR](https://github.com/ACL4SSR/ACL4SSR) — 上游规则集
- [zsokami/ACL4SSR](https://github.com/zsokami/ACL4SSR) — 本配置的修改基础
