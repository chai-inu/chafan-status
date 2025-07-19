---
title: "茶饭开发动态 0719 - 社区建设上需要大家的协助"
date: 2025-07-19
---

大家好，

[茶饭内测](https://status.cha.fan/2025/07/08/closed-beta.html)到现在已经两个星期了。好消息是，到现在并没有出现数据损坏和丢失的问题。同时，茶饭没有任何非预期的 down time. 说人话就是，除了我为了部署新版本的茶饭而重启 fastapi 进程外，茶饭的后端一直是正常运行的。不过，在正式上线前我需要对 Database Schema 进行调整，这是一个风险很高的操作。我希望我能在下周开心地和大家说，No news is good news.

** [内测开始](https://status.cha.fan/2025/07/08/closed-beta.html)时已经正常运行的功能 ✅  **
- 创建提问和回答
- 创建专栏，发表文章
- 创建圈子 （但请不要单纯为了测试和灌水而去创建新的圈子） 

** 0719 版本添加的新功能 💡**
- [RSS 订阅圈子动态](https://discord.com/channels/807057763234349087/807057763234349090/1393043643404779580) - 例如 https://api.cha.fan/api/v1/rss/site/meaningless/rss.xml
- 修复（部分重写）了用户 Feed。现在可以在茶饭主页看到自己关注的人的动态。但现在仅支持提问和回答。发布评论，发布专栏等动态暂不支持
- 修复了通知功能。当自己被回答、被评论时，右上角会有提示 （和茶饭1.0一致）
- 移除了 Reaction （emoji）功能

** 当前的 blocker 🛑 **
- 关注用户的动态未包含评论和专栏
- [无法发送私信](https://github.com/chafan-dev/chafan-pwa/issues/424)
- [圈子管理功能基本不可用](https://github.com/chafan-dev/chafan-pwa/issues/423)
- [阅读数统计是错的](https://github.com/chafan-dev/chafan-pwa/issues/420)
- [无法 at 其他用户](https://github.com/chafan-dev/chafan-pwa/issues/414)
- [GET /question 会回源](https://github.com/chafan-dev/chafan-pwa/issues/412)

在社区管理上，有几件事需要大家的协助

#### 长期闲置的提问 
在茶饭 1.0 时期，就有很多问题长期没有回答和评论。在迁移过程中，这样的问题就更多了。我打算关闭一些时效性较强但没有回答和评论的提问。如果你对某个问题感兴趣，希望这个提问被保留，可以为提问发一条评论，也可以联系狗管理表达自己的兴趣。

#### 欢迎认领闲置的圈子(site) 
如果一个圈子的原管理员没有提交表格，那圈子就会被 assign 给猫管家，例如 [PlayStation圈子](https://cha.fan/sites/PlayStation). 在 [圈子列表](https://cha.fan/explore?tab=sites) 里，可以看到很多有零个问题的圈子。在接下来，我会考虑关闭一些圈子。那非常希望大家联系狗管理，认领自己感兴趣的圈子。

另外，茶饭2.0的前端和后端代码都已经开源。[前端部分](https://github.com/chafan-dev/chafan-pwa)有了简明的开发指南，但 [后端部分](https://github.com/chafan-dev/chafan-core)的开发指南还没有更新。如果有朋友感兴趣的话可以告诉我，我会尽快更新后端的开发指南。

现在茶饭不支持图片上传功能，我之前也没有搭建图床的经验。我搜索一些资料后，想到了几种可能的方案，想咨询一下大家的建议
```
方案A：我自己 selfhost S3 (MinIO?)， chafan 1.0 的对接 AWS S3 的代码可以比较容易地迁移过去
方案B：selfhost 一个图床服务，但不确定用什么更好
方案C：使用 cloudflare 的 S3 服务 （还不确定实际开销会多大，我希望让这部分的硬性开销低于 2 usd/mo)
方案D：找一个提供廉价商业服务的图床
```


最后，再次感谢您对茶饭的支持！

[狗管理 @chai_inu](https://cha.fan/users/chai_inu)
