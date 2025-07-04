---
title: "054-递延所得税资产和递延所得税负债审计要点"
type: posts
cover: https://github.com/richbridge/picx-images-hosting/raw/master/thumbnail/投技.jpg
categories: [投技]
tags: [IPO审计手札]
date: 2023-08-01
---
这哥俩很会计，核心审计程序只是重新计算；这哥俩很折腾，最终定数取决于其他科目

递延所得税底稿并不难刷，**等别人数字敲定，你往底稿一涂**，自带的公式一测算，调整分录一出，三表一链，完事

![](https://img.richfan.site/ibank/IPO审计札记/054-递延所得税资产和递延所得税负债审计要点_1.webp)|

不明就里的小朋友，**秉持世间万物皆可套，也能抄得有模有样**

刷底稿易，明就里难，尤其是《企业会计准则解释第 16 号》横空出世

我班门弄斧一波，我有一家平平无奇的公司，平平无奇的25%所得税率，平平无奇的

利润总额 50W，我的生产线计提资产减值损失 50W，所得税几何

所得税费用=当期所得税+递延所得税

当期所得税=应纳税所得额 X 所得税税率

应纳税所得额＝税前会计利润（利润总额）＋纳税调整增加额－纳税调整减少额

两个疑问：**why纳税调增，调增50W+why确认递延**

计算当期

借：所得税费用——当期所得税：25W（利润总额 50+纳税调增 50)

贷 ：应交税费——应交所得税：25W（不难看出：**孝敬税局只与当期有关，因为只有通过应交税费核算的才需要花真金白银**，，，若不纳税调增，我再计提 50W 减值岂不是今年无需纳税）

计算递延

借：递延所得税资产 ：12.5W（生产线的计税基础大 50W）贷：所得税费用——递延所得税：12.5W

不难看出：纳税调增事项（生产线计提减值这件事）一借 12.5W 一贷 12.5W，**对当期税相关的损益没有半毛钱影响，通过递延所得税资产这种伪资产平衡掉了**

伪资产也终会烟消云散，因其入表靠的就是暂时性差异

时过境迁，又是一年，又是 50W 的利润总额，我把生产线给卖了

去年计提减值，分录如下

借：资产减值损失：50W

贷：固定资产减值准备：50W

今年卖线，分录如下

借：固定资产清理：N-50

借：固定资产减值准备：50（**没有影响今年的利润表，故而纳税调减，有增必有减**）贷：固定资产：N

计算当期，（利润总额 50-纳税调减 50）X25%借：所得税费用——当期所得税：0W

贷 ：应交税费——应交所得税：0W（所谓未来少交税，现在多交税，置身此情此景即**去年交了税，今年不交了**）

暂时性差异无了，平衡项也得说拜拜

借：所得税费用——递延所得税 ：12.5W（**平衡项的意义在于实现会计口径的损益不受影响**，税局觉得所谓不好测，不便拿捏的减值，是完完全全符合会计准则滴，是减值了才公允可靠滴，势在必减）

贷：递延所得税资产：12.5W

**税这种底稿，得做N年一期方见其妙**

《企业会计准则解释第16号》：对于如果一项交易同时确认资产和负债、且产生等额的应纳税暂时性差异和可抵扣暂时性差异，**诸如承租人在租赁期开始日初始确认租赁负债并计入使用权资产，固定资产因存在弃置义务而确认预计负债并计入固定资产成本**

需要在交易发生时分别确认相应的递延所得税负债和递延所得税资产。同时，从报表可比性和实务需要出发，这条生效日期与国际财务报告准则保持一致（自2023年1月1日起实施）

非常蛋疼，我估计**以XXX的水准，到时候又是群魔乱舞**

《企业会计准则第18号——所得税》有一条很好玩：企业应当以很可能取得用来抵扣可抵扣暂时性差异的应纳税所得额为限，确认由可抵扣暂时性差异产生的递延所得税资产

审计底稿如何陪她玩，某些流派直接飞机，直接不管；某些流派审计说明以当前盈利与否定性下结论；某些流派开始装逼：**取得企业管理层批准的最近的通过正常的生产经营活动能够实现的应纳税所得额相关的财务预算或预测数据**，检查其预算及预算的合理性。。。

呆的企业没得预算，也不会算，牛的企业算了也得保密。。。即使给了，预算这门学问大多审计师也拿捏不住，，，哪来那么多时间与精力这样玩

新疆证监局曾警示过希格玛：新赛股份 2020 年末递延所得税资产余额 661.75 万元，

其中新疆乌鲁木齐新赛油脂有限公司、新赛精纺等新赛股份6家子公司期末递延所得

税资产合计 487.71 万元。这 6 家公司**均处于未分配利润为负、连续亏损且累计金额较大状态，未见可抵扣亏损在未来可以弥补的充分依据**，且新赛股份对上述部分公司长期应收款及长期股权投资计提了减值准备。你们未充分关注到上述事项对递延所得税资产期末余额确认的影响，未获取充分审计证据。

这件事之所以好玩，想要确认的公司，会玩了命嚷嚷：**我未来一定能盈利，有足够的应纳税所得额**；不想确认的公司，会大义凛然曰：**未来不确定，我谨慎处理不确认**。

《关于广州慧智微电子股份有限公司 IPO 审核问询函中有关财务事项的说明》

![](https://img.richfan.site/ibank/IPO审计札记/054-递延所得税资产和递延所得税负债审计要点_2.webp)|