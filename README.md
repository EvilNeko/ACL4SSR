## 注意
本项目是基于 https://github.com/zsokami/ACL4SSR 修改的自用版

## 配置文件

### Full 版（含地区分组）

无 DNS 泄漏：

https://raw.githubusercontent.com/EvilNeko/ACL4SSR/main/ACL4SSR_Online_Full_Mannix_No_DNS_Leak.ini

无 DNS 泄漏（去除 no-resolve）：

https://raw.githubusercontent.com/EvilNeko/ACL4SSR/main/ACL4SSR_Online_Full_Mannix.ini

### 精简版（去除地区分组，仅保留核心策略组）

有 DNS 泄漏防护（no-resolve）：

https://raw.githubusercontent.com/EvilNeko/ACL4SSR/main/ACL4SSR_Online_Mannix_No_DNS_Leak.ini

无 DNS 泄漏（去除 no-resolve）：

https://raw.githubusercontent.com/EvilNeko/ACL4SSR/main/ACL4SSR_Online_Mannix.ini

## 分组改动

- 改名：✈️ 起飞 → ✈️ 选择节点（ruleset 引用同步更新）
- 去除：🇹🇼 台湾 / 👆🏻🇹🇼 台湾
- 新增：🇬🇧 英国 / 👆🏻🇬🇧 英国
- 总顺序：选择节点 → 低延迟 → 指定 → 中国 → 香港 → 美国 → 英国 → 新加坡 → 日本 → 其他 → 手动指定组（👆🏻 同序）→ 墙内 / 广告 / B站 / AI / 未知站点
- 手动指定组（👆🏻 前缀）的更改与顺序同理

⚠ 每个组名的空格后面都添加了一个隐藏字符 `\u200d` 用于防止与节点重名，改名需谨慎
