# 豆包商店插件包

本目录即上传到豆包开放平台的**商店插件**内容。根目录须为 `plugin.json`、`mcp.json`、`skills/`（不要多包一层 `doubao` 文件夹）。

## 打 zip

在 `doubao` 目录内选中：

- `plugin.json`
- `mcp.json`
- `skills/`

压缩为 zip。解压后第一层就要能看到上述三个条目。

## MCP

- 地址：`https://geo.wenjjiegeo.cn/api/tlrai/mcp`
- 类型：`streamable-http`
- 暂不需要在 `mcp.json` 里写口令；认证走豆包开放平台配置（商店 ISV 长期建议 OAuth）。

## 工具（由服务端 `tools/list` 提供）

| 工具 | 用途 |
|------|------|
| `save_company` | 保存已确认的公司与产品资料 |
| `generate_title` | 为选定的一款产品生标题 |
| `generate_article` | 为选定的一款产品生正文 |
| `diagnose_geo` | 仅输出已测到的诊断结果 |
| `plan_geo` | 仅根据未通过项写要加强的地方 |

## 技能

- `geo-write`：对话流程与工具调用顺序（必读）

`geo-auth`、`geo-publish` 面向 DSH 本机发布，豆包商店包可保留或删除，不影响 MCP 连远端。