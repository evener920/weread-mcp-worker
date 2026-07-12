# Changelog

## 0.1.1 - 2026-07-12

### 修复

- 修复微信读书 Agent API Gateway 返回“插件版本过旧”或 `upgrade_info` 的问题。
- 将上报给微信读书网关的 `skill_version` 从 `1.0.3` 升级到 `1.0.4`。

### 变更

- 新增统一的默认微信读书 Skill 版本常量，避免版本号散落在多个文件中。
- 同步微信读书 Skill `1.0.4` 的 `profile` 行为：
  - `weread_get_profile` 默认 `progressLimit` 从 `10` 调整为 `5`；
  - `weread_get_profile` 默认 `highlightCountLimit` 从 `5` 调整为 `0`；
  - 默认只获取最近 5 本电子书的阅读进度，笔记概览使用 `/user/notebooks`。
- 同步微信读书 Skill `1.0.4` 的 deepLink 规则：
  - 优先使用接口返回的 `deepLink`；
  - 不再主动拼接 `weread://` 深度链接；
  - 保留普通网页 `webUrl` 作为辅助链接。
- 更新 README、示例环境变量、测试和 Worker 默认配置到微信读书 Skill `1.0.4`。

## 0.1.0 - 2026-05-16

### 新增

- 初始发布：基于 Cloudflare Worker 的单用户微信读书 MCP Server。
- 支持加密 URL 路径、Setup 页面、微信读书只读 MCP tools、一键安装脚本和敏感信息检查。
