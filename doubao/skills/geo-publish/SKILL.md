---
name: geo-publish
description: 对方明确说「一键发布」时，在这台电脑上打开发布页。不把稿子送进界问队列。小红书不代填。
metadata:
  display_name: GEO 发布
  display_description: 对方说一键发布时，只在本机打开发布页。
---

# 本机发布

这个技能内置在本 Agent 里。发布在对方自己的电脑上完成。

默认不发布。对方没有明确说「一键发布」，就不要运行命令。

1. 只发他这一次点了名的平台，并且稿子已经写在本地文件里。没点名的平台不发。
2. 小红书只把文案留在本地，不运行发布命令。
3. 先确认这个平台已经用对方自己的账号授权。输出不是「已授权」就停，按技能 `geo-auth` 询问并打开授权窗口：

```
powershell -NoProfile -File "$env:DSH_HOME\run-py.ps1" authorize_local.py --has 知乎
```

4. 把稿子放进本机发布页。`--file` 换成稿子的实际路径，`--platform` 换成他点的平台，`--index` 是第几篇，从 1 开始。多篇就一篇一篇跑：

```
powershell -NoProfile -File "$env:DSH_HOME\run-py.ps1" publish_local_file.py --file "稿子.md" --platform 知乎 --index 1
```

5. 标准输出里要有「已在侧边栏打开」，后面那一行是地址。把这个地址写成可点击链接。没有这一句，或输出「未授权」，就停。其他失败只说「这次没有完成」，不要贴命令输出。
6. 不把稿子上传到界问队列，也不运行 `publish_agent_py.py`。
