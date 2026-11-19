---
name: geo-write
description: 对方要做 GEO 标题或文章时使用。先确认公司资料并调用 save_company，再调用 generate_title 或 generate_article。没有公司资料时不要生标题或生文。不编造客户、数字、效果和资质。
metadata:
  display_name: GEO 生文
  display_description: 按已确认的公司资料生标题和文章。
---

# GEO

公司资料必须是对方确认过的事实。没确认就不要写。

1. 对方确认资料后，调用 `save_company`。
2. 要标题时调用 `generate_title`，要正文时调用 `generate_article`。`task` 写平台和篇数。
3. 没有公司资料时，工具会要求先保存。这时不要自己写稿。
4. 成稿只交工具返回的正文。不要复述规则，不要提到口令、服务器或接口。
