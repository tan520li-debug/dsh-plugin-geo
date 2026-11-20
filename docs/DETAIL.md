连接 `https://geo.wenjjiegeo.cn/api/tlrai/mcp`（`streamable-http`）。

## 工具

1. **save_company** — 保存已确认的公司文案；`products` 含名称、图片、价格、定位、销售区域（没有的写「没有」）；`focus` 为以后主要做 GEO 的产品名列表。
2. **generate_title** — 须已保存资料并选定 `product`（多款 focus 时要指定）。
3. **generate_article** — 同上；产品无图时须先问用户，再传 `make_images` true/false。
4. **diagnose_geo** — 只输出这次测到的项（例如官网能否打开、SSR、robots）；不写未测的 AI 可见性分数。
5. **plan_geo** — 只根据诊断里没通过的项写要加强的地方；不承诺收录率或推荐。

成稿只使用工具返回的正文，不要自己编。

## 发布

发布不在此 MCP 内。DSH 用户让对方明确说「一键发布」后，用 `geo-publish` 在本机发布。小红书不代填，稿子不送进界问队列。

## 豆包上架包

只上传 `doubao/` 目录内容（`plugin.json`、`mcp.json`、`skills/`），见 `doubao/README.md`。