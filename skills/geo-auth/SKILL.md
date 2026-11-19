---
name: geo-auth
description: 发布前由 AI 打开授权窗口。用户登录后点「已完成授权」，校验通过变成「授权成功」并保存登录态。
metadata:
  display_name: GEO 授权
  display_description: 用对方自己的账号打开授权窗口，并保存登录态。
---

# 平台授权

对方要发布、或点名的平台还没授权时，由你先问，不要等对方来找授权入口。授权在对方自己的电脑上完成。

同一条回复里做完这三件事：

1. 问他这次要授权哪些内置平台。他已经点了名，就按他点的来，不要再改成别的平台。
2. 告诉他：用自己的账号登录授权窗口，然后点窗口右上角「已完成授权」。按钮变成「授权成功」才算登录态已经保存。不要用这台电脑上原来已经登录过的浏览器。
3. 自动打开授权窗口。一次只开一个，开着就不要再开：

```
powershell -NoProfile -File "$env:DSH_HOME\run-py.ps1" authorize_local.py --serve
```

再打开授权窗口。`--platforms` 换成他点的平台，多个用逗号：

```
powershell -NoProfile -File "$env:DSH_HOME\run-py.ps1" authorize_browser.py --platforms 百家号
```

标准输出出现「已打开登录页」就告诉他去那个窗口登录，并点右上角「已完成授权」。出现「授权成功」才算登录态已保存。不要复述登录态文件，不要把密码发到对话里。

核对时只看这一句：

```
powershell -NoProfile -File "$env:DSH_HOME\run-py.ps1" authorize_local.py --has 知乎
```

输出「已授权」才算这个平台授权完成。其他失败只说「这次没有完成」。
