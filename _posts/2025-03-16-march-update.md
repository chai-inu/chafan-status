---
title: "三月份的更新"
date: 2025-03-16
---


您好，

我是狗管理 chai_inu。今天花一点时间，向大家汇报一下迁移进度。

之前的调查问卷 https://status.cha.fan/2025/02/17/migration.html 收到了很多份回复，在备注里看到了很多让我备受鼓舞的留言。"您的支持是我们最大的动力" 这句话被各种商家用作宣传语。但在用爱发电的茶饭，这是对站点的一句平实的描述。在这里再次地感谢大家，再过去的几年里对茶饭一路的支持。也恳请大家在未来，继续支持茶饭。

我收到原站长 izgzhen 导出的数据以后，尝试导入回 PostgreSQL，却遇到了不少 Data Type Error. 在反复的 Back-and-Forth 之后，数据导入的问题基本已经修正了。我不是专业程序员，写一些茶饭的代码有些赶鸭子上架，好在我旱鸭子摸着石头过河，这部分的 blocker 是基本解决了。

但 question-answer-relation 是一个棘手的问题。用户 A 创建了问题 Q1，但 A 没有提交问卷。用户 B 对 Q1 的回答就无法导入数据库。我准备执行的解决办法是，为每位用户创建一个专栏，将导入失败的回答在专栏中发表。等茶饭上线后，再决定是否重新创建问题。


answer-comment-relation 也会面临同样的问题。用户 A 发的评论 C1，用户 B 仅回复一句 "赞同/反对"。如果没有导入 C1，那用户 B 的评论也就失去了价值。现在我手头的 dataset 里，这种找不到 parent comment 的评论大概有900条。我可能会暂时搁置他们，再考虑是否用半自动或人工的方式将其导入。

最后，在这里分享一下我下一步的计划，也征求一下大家的意见。我在解决上述问题后，打算先上线一个只读的茶饭 2.0. 大家可以先浏览原有的问题和回答，检查自己的数据是否被正确恢复。从管理员的角度看，我也可以测试代码运行是否稳定，让服务器暴露在爬虫之下，进行负载的压力测试。为了让大家可以在未登录情况下看到完整的茶饭的内容，也为了简化后端的代码，我准备移除原有的温和 login-wall，包括专栏的 login-wall。



再次感谢您对茶饭的支持！

狗管理 @chai_inu
