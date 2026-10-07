---
layout: default
title: "Single-exponential recovery and bounded-price strictness for metric $k$-median"
family: "125"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Single-exponential recovery and bounded-price strictness for metric `@@M@@k@@`-median

> 结果族 125：The metric `@@M@@k@@`-median approximation threshold and recovery　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文为度量 `@@M@@k@@`-中值（metric `@@M@@k@@`-median）问题打造两件工具：坏簇数仅为对数时仍可多项式完成的"锚点恢复"算法，以及对剩余构造一次相容执行的"有界价格严格性"支付论证；合并后首次在一般有理度量上得到严格小于 2 的随机 `@@M@@(2-\sigma)@@`-近似。

## 问题背景

度量 `@@M@@k@@`-中值问题给定客户集 `@@M@@D@@`、候选设施集 `@@M@@F@@`、整数 `@@M@@k@@` 与度量距离，要求选至多 `@@M@@k@@` 个设施 `@@M@@S@@` 最小化 `@@M@@\operatorname{cost}(S)=\sum_{p\in D}d(p,S)@@`。它是聚类与设施选址理论的核心模型：LP 舍入（Charikar–Guha–Tardos–Shmoys）、原始-对偶方法（Jain–Vazirani）、对偶拟合与交换局部搜索（Arya 等，`@@M@@3+\varepsilon@@`）先后给出常数因子；Li–Svensson 的伪近似约化与后续 bi-point 舍入推进到 2.675、2.613，Cohen-Addad–Grandoni–Lee–Schwiegelshohn–Svensson（CGLSS，STOC 2025）达到 `@@M@@2+\varepsilon@@`。真正的拦路虎是"设施预算"：允许少量额外设施的松弛解容易构造，而每个输出都严格开至多 `@@M@@k@@` 个设施、同时把费用压到 2 以下，此前没有分析能做到。本文在 CGLSS 架构上补齐两块短板：恢复步对例外簇数的依赖降到单指数，支付步与一次实际执行的预算完全相容。

## 主要结果

其一，精化恢复定理：在距离为不超过 `@@M@@N@@` 固定多项式界的正整数的归一化度量上，设锚点（anchor）`@@M@@S@@` 有 `@@M@@h@@` 个设施，若存在同规模比较解 `@@M@@O@@`（费用 `@@M@@P@@`），其簇分为好簇与坏簇（bad center），好簇各有 `@@M@@S@@` 中互异代理（proxy），代理指派总费用至多 `@@M@@P_g+\mu P@@`（`@@M@@\mu\le\min\{1/4,\varepsilon/12\}@@`），坏簇数 `@@M@@m\le L_0\log N@@`，则只输入 `@@M@@S,\mu,L_0,\zeta@@` 的随机算法恒有 `@@M@@|\widehat S|\le h@@`，且以概率至少 `@@M@@1-\zeta@@` 达到 `@@M@@\operatorname{cost}(\widehat S)\le(1+2/e+\varepsilon)P@@`，时间对 `@@M@@m@@` 单指数、对 `@@M@@N@@` 多项式。其二，有界价格严格性（bounded-price strictness）：对 CGLSS 对数剩余构造的一次相容执行，若常规开设支付 `@@M@@\lambda\le TP_C@@`，则 `@@M@@\sum_{p\in C}\alpha_p\le\lambda+(2-c(T)/2)P_C@@`，`@@M@@c(T)>0@@`。其三，全局应用：存在绝对常数 `@@M@@\sigma>0@@`，使任意有限有理度量上的随机多项式算法总开至多 `@@M@@k@@` 个设施，以至少 `@@M@@1-(|D|+|F|+2)^{-a}@@` 的概率且在期望意义下费用 `@@M@@\le(2-\sigma)\operatorname{opt}_k@@`。

## 证明思路

恢复轨道从真实锚点出发，比较解只在分析里用来识别"有利随机历史"。状态由 `@@M@@S@@` 的幸存成员与挂在被采样客户上的叶子哑元（leaf dummy）组成；每步按客户到参考集的距离成比例采样，再在其周围猜一个球（ball），或移除其当前服务的原设施。半径菜单由总体半径控制，大菜单下标只出现在互不相交的客户集上，其比较费用恰好支付半径，故不利历史的总概率为 `@@M@@\exp(-O(m))@@`——这正是单指数依赖的来源，使 `@@M@@m=O(\log N)@@` 时仍多项式可行。算法保存每一步前缀，无需知道比较划分即可停在有用状态。补全阶段：落在无球覆盖的坏中心处的移除目的地由精确子集动态规划优化；其余目的地用"每球取一设施、最大化单调次模节省（monotone submodular saving）"决定，分区约束的类别连续贪心给出 `@@M@@1-1/e@@` 期望增益，把超支 `@@M@@2P@@` 中的 `@@M@@1-1/e@@` 比例省下、只剩 `@@M@@2P/e@@`，合计恰为 `@@M@@1+2/e@@`。构造每移除 `@@M@@m@@` 个原设施至多新增 `@@M@@m@@` 个，预算严格成立；精化一节再用两次相继的停时规则把估计收紧到 `@@M@@1+2/e+\varepsilon@@`。

支付轨道固定剩余构造的最终价格 `@@M@@\lambda@@` 与副本长度，只重放其最终有效序列：一个客户预算势支付常规开设，相位的精确极大性给出"不超额叫价"不等式；证明把客户移除排序并取后缀最大值，两个互补松弛（complementary slackness）估计表明所有预算不等式同时近等式会强制早、晚期行为不相容，从而得到与客户数无关的有界价格缺口。

最后合并，令 `@@M@@L=O(\log N)@@`：若把预算从 `@@M@@k@@` 降到 `@@M@@k-2L@@` 最优几乎不变，则在目标 `@@M@@k-L@@` 上运行剩余构造，剩余腾出空间、严格性把费用压到 2 以下；否则由乘积论证存在对删中心敏感的基数 `@@M@@h'@@`，其最优解满足簇分离 `@@M@@n_i\operatorname{sep}_i\ge\beta P@@`，锚定后只留 `@@M@@O(L)@@` 个坏簇，恢复算法给出 `@@M@@1.97(1+\xi)@@`。算法把两种情形的候选都算出并取最便宜者，全程不测试任何最优值；再用度量舍入引理把整数度量结论转移回一般有理度量，常量选取使 `@@M@@(2-\gamma)(1+\gamma/16)^2\le2-\gamma/2@@`，期望再吸收失败事件即得 `@@M@@2-\sigma@@`。

## 可信度与备注

本文主结果已 Lean 形式化，是族 125 中验证状态最好的一篇。姊妹篇《The approximation threshold for metric k-median》在同一候选设施模型上给出确定性的 `@@M@@(1+2/e+\varepsilon)@@` 近似，其图舍入证明与本文的恢复/支付证明相互独立，两篇合并构成族 125 的完整图景：确定性阈值 `@@M@@1+2/e@@`，随机可到 `@@M@@2@@` 以下。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文虽已形式化，但全局应用把 CGLSS 的对数剩余构造当作外部输入，该外部部分仍请以原文与社区核验为准。

{% endraw %}
