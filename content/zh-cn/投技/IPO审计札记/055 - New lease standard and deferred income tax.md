---
title: "055-新租赁准则与递延所得税"
type: posts
cover: https://jsd.cdn.zzko.cn/gh/richbridge/picx-images-hosting@master/thumbnail/投技.jpg
categories: [投技]
tags: [IPO审计手札]
date: 2023-08-01
---
《企业会计准则解释第16号》关于单项交易产生的资产和负债相关的递延所得税不适用初始确认豁免的会计处理惜字如金，整了一顿火星文，**小子不才，实务演示一番**

借：使用权资产=254.60

借：租赁负债——未确认融资费用=31.91贷：租赁负债——租赁付款额=286.51

调完这笔，关机下班

然**准解16号横空出世，得再调一笔，才能下班**

借：递延所得税资产——租赁负债=254.60*25%=63.65（具体税率视企业实际情况

而定）

贷：递延所得税负债——使用权资产=63.65

**这条常识是前提，别忘了**：如若估计未来一直亏损，可能无法取得足够的应纳税所得额，那么递延所得税资产的确认**只能以未来能取得多少可以抵扣可抵扣暂时性差异的应纳税所得额为限**，而不能以实际的可抵扣暂时性差异金额为基础

![](https://img.richfan.site/ibank/IPO审计札记/055-新租赁准则与递延所得税_1.webp) 

看似很麻烦，实则用不了三十秒，**若究背后原理，其实三分钟也能道明白**

税法规定，以经营租赁方式租入固定资产发生的租赁费支出，按照租赁期限均匀扣除；此时此刻，由于**税法上不允许承租人在税前扣除使用权资产的折旧费用**(也许有点小绕，这么说吧：使用权资产是靠折旧，一点一点折完的，租赁费的支出关联的是租赁负债），故而使用权资产允许未来税前扣除的金额为 0=计税基础为 0

准则规定，**负债的计税基础是指负债的账面价值减去未来期间计算应纳税所得额时按照税法规定可予抵扣的金额**，由于租赁负债=未折现的租赁付款额-未确认融资费用，其账面价值小于税法上允许未来分期扣除的租赁费支出（ 未折现的租赁付款额 286.51），故而租赁负债的账面价值未来期间计算应纳税所得额时可以全部扣除=计税基础为0

车轱辘话瞅不明白也没关系，**依葫芦画瓢，照着套套完事，继续跟进**

借：管理费用等（谁收益谁承担）=254.6+5=50.92贷：使用权资产累计折旧=50.92

借：递延所得税负债——使用权资产=254.6-50.92=203.68*25%=50.92

贷：所得税费用——递延所得税费用=50.92借：财务费用=254.6*5%=12.73

贷：租赁负债——未确认融资费用=12.73

借：租赁负债——租赁付款额=50.27（书接上回）

贷：银行存款等=50.27

借：所得税费用——递延所得税费用=254.6-50.27+12.73=217.06*25%=54.27

贷：递延所得税资产——租赁负债=54.27

**计税基础一直是0，拿租赁的知识点算出账面价值的变化即可**，两笔分录写一块也行，差额系所得税费用，可借可贷

以后年度怎么玩，一样一样滴，**使用权资产折旧多少，账面价值与计税基础的差距就缩小多少**，递延所得税负债就反方向冲回对应税率的多少。。。

以上规定自 2023 年 1 月 1 日起施行，允许企业自 2022 年度提前执行

大所何以为大所， 不快人一步， 何以彰显逼格， 何以彰显技术优势， 何以自我感动，质控 KPI+1

米土：**过去以科目为导向的审计思路，可能更多的需要转变到以业务为导向上来**