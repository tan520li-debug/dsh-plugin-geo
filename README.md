# GEO优化

把界问的 GEO 接到 **DSH** 或 **豆包**。公司资料须先由对方确认再保存；一次只推广选定的一款产品。

**MCP 地址**：`https://geo.wenjjiegeo.cn/api/tlrai/mcp`

## 工具

| 工具 | 说明 |
|------|------|
| `save_company` | 保存公司与产品（名称、图片、价格、定位、销售区域、`focus`） |
| `generate_title` | 为选定产品生标题 |
| `generate_article` | 为选定产品生正文（无图时会先问要不要生图） |
| `diagnose_geo` | 只写已测到的结果，不写未测项 |
| `plan_geo` | 只根据没通过的测量写要加强哪里 |

不要编造客户、数字、效果和资质。提示词在服务端，不在本仓库。

可以不带口令连接；暂不设免费到期日。有口令时按订阅隔离资料。

## DSH

插件页选「安装第三方插件」，填 Git 地址：

`https://github.com/tan520li-debug/dsh-plugin-geo`

装好后新开一轮对话。发布走 `geo-publish` 技能，须对方说「一键发布」，且本机有 `run-py.ps1`。

## 豆包

### 商店插件（应用市场）

用仓库里的 **`doubao/`** 目录打 zip（见 [doubao/README.md](doubao/README.md)），在豆包开放平台提交**商店插件**审核。

### 自建连接器（不走市场）

豆包工作 → 自定义连接器 → HTTP → 填上面的 MCP 地址，请求头留空。

## 文档

- [docs/DETAIL.md](docs/DETAIL.md) — 行为说明  
- [docs/发布渠道备忘.md](docs/发布渠道备忘.md) — 豆包市场 / mcp.so 等渠道记录