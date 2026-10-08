---
layout: default
title: "Uniform indices for semi-log-canonical log Calabi–Yau pairs"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform indices for semi-log-canonical log Calabi–Yau pairs

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

设想一堆"近似平衡"的账本：每本的余额都声称是零，但记账单位不同——有的以半元记账，有的以三分之一元记账，要各自乘上不同倍数才能抹平小数。这篇论文证明：只要账本的维数和允许出现的记账单位（系数）固定，就存在一个公共倍数，把所有这类账本一次性抹平——不管每本账由多少页粘成。

**关键词卡片**

- log Calabi–Yau 配对（log Calabi–Yau pair）：满足 `@@M@@K_X+B\sim_{\mathbb Q}0@@`（有理平凡）的配对。
- 指标（index）：使 `@@M@@m(K_X+B)@@` 同时 Cartier 且线性平凡的最小正整数 `@@M@@m@@`。
- 半 log 典范（semi-log-canonical, slc）：允许分支沿"双重轨迹"粘合的温和奇性等级，模空间中极限点的标准类型。
- 一致界（uniform bound）：只依赖维数与系数集、不依赖具体配对的公共常数。

**看个具体例子**

一维玩具样本：`@@M@@X=\mathbb{P}^1@@`，`@@M@@B=\tfrac12(P_1+P_2+P_3+P_4)@@`。则 `@@M@@K_X+B=-2+2\sim 0@@`，是 log Calabi–Yau；但系数是半整数，须取 `@@M@@m=2@@` 才 Cartier——指标为 `@@M@@2@@`。若再把若干条这样的曲线沿节点两两粘合（slc 的典型构造），各页的平凡化在粘合处未必吻合，指标可能更复杂。定理（数字版）：固定维数 `@@M@@d\ge 4@@` 与系数集 `@@M@@\Phi@@` 后，存在 `@@M@@a(d,\Phi)@@`，使一切等维 slc 配对都有 `@@M@@a(d,\Phi)(K_X+B)@@` Cartier 且平凡，与分支个数、粘合方式都无关。

**为什么值得关心**

一致指标是模空间理论（slc 配对作极限点）能被有限参数化的算术基础；结合三维及以下的已知结果，本文彻底解决了有限有理系数版本的 slc 指标猜想。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
论文证明了半对数典范（semi-log-canonical, slc）log Calabi–Yau 配对的一致指标定理：固定维数 `@@M@@d\ge4@@` 与有限有理系数集 `@@M@@\Phi@@` 后，存在仅依赖 `@@M@@d@@` 和 `@@M@@\Phi@@` 的倍数 `@@M@@a(d,\Phi)@@`，使 `@@M@@a(d,\Phi)(K_X+B)@@` 同时 Cartier 且线性平凡，与 `@@M@@X@@` 的连通分支个数无关。结合 Jiang–Liu 的三维及以下结果，这彻底解决了有限有理系数 slc 指标猜想。

## 问题背景
log Calabi–Yau 配对 `@@M@@(X,B)@@` 满足 `@@M@@K_X+B\sim_{\mathbb{Q}}0@@`，其指标（index）是使该除子 Cartier 且线丛平凡的最小正整数——它衡量"有理平凡"与"真正平凡"之间的差距。Gongyo 已知这样的指标存在，但可能依赖配对本身；指标猜想（Jiang–Liu 猜想 1.5 的有限有理系数版本）问：固定维数与系数集合后能否有公共倍数。非正规情形另有一层下降（descent）困难：slc 配对允许正规分支沿双重轨迹（double locus）相交，各分支规范化上的平凡化未必在粘合处吻合。这类一致界对模空间理论至关重要——slc 配对正是模问题中极限点的奇性类型。此前 Jiang–Liu 解决了三维及以下和四维非 klt lc 情形，Birkar 解决了有理连通 klt 配对；高维一般 slc 情形悬而未决。值得注意的是 Singh 构造了指标随维数双指数增长的光滑 Calabi–Yau 界，故一致界必须依赖维数。

## 主要结果
定理 1.1：设 `@@M@@k@@` 为特征零的代数闭域，`@@M@@d\ge4@@`，`@@M@@\Phi\subset[0,1]\cap\mathbb{Q}@@` 有限。则存在整数 `@@M@@a(d,\Phi)>0@@`，使得对任何连通射影等维 slc log Calabi–Yau 配对 `@@M@@(X,B)@@`（维数 `@@M@@d@@`、`@@M@@B@@` 的非零系数均属 `@@M@@\Phi@@`），有 `@@M@@a(d,\Phi)(K_X+B)@@` Cartier 且 `@@M@@\mathcal{O}_X(a(d,\Phi)(K_X+B))\simeq\mathcal{O}_X@@`。要点有二：界不依赖 `@@M@@X@@` 的不可约分支个数与双有理模型上 lc 层的个数；且它是公共平凡化倍数，一次性同时清除局部 Cartier 指标与整体挠。与 Jiang–Liu 三维定理合并，即得有限有理系数 slc 指标猜想的完全解答。

## 证明思路
证明遵循"正规到 slc"的经典策略，先由姊妹篇《Uniform Pluricanonical Iitaka Fibrations》的一致正规指标定理取一个仅依赖 `@@M@@d,\Phi@@` 的偶数 `@@M@@m@@`，在每个规范化分支上平凡化表现为带指定对数极点的有理 `@@M@@m@@`-典范形式 `@@M@@\theta_i@@`。先在 crepant dlt 模型上取对数留数（logarithmic residue），把它限制到导体（conductor）层上；在一般节点处，两侧留数相差非零标量 `@@M@@r_e@@`。以规范化分支为顶点、一般节点为边的有限图上，同时匹配所有 `@@M@@\theta_i@@` 等价于让每条闭路上留数比的乘积为一，因此只需这些乘积的阶一致有界。为此论文把闭路翻译为双有理自同构：极小 lc 层是 klt 的，分支内部用 Kollár 的 `@@M@@\mathbb{P}^1@@`-链接定理在偶次数下留数不变地连接任意两个极小层，跨边则证明带乘子 `@@M@@r_e@@` 的双有理留数比较（第 7 节，含非分裂节点与最终 `@@M@@S_2@@` 延拓）。于是闭路诱导某个极小 klt 层上 crepant 双有理自映射，它作用在平凡化形式上恰为边比之积。问题化归为核心的一致性定理：对满足 `@@M@@m(K_V+\Delta)\sim0@@` 的射影积分 klt 配对，用 `@@M@@\dim V@@` 与 `@@M@@m@@` 界定 crepant 自映射作用于平凡 `@@M@@m@@`-典范形式的标量阶。这里用 Matsumura–Wang 分解把配对拆成有理连通因子、阿贝尔因子与既约 Calabi–Yau/辛因子：有理连通因子由有界性与多重典范表示控制，其余因子上特征出现在整系数上同调中。具体地考察包含全纯顶形式的极小有理 Hodge 子结构 `@@M@@T(U)\subset H^n(U,\mathbb{Q})@@`，它双有理不变且带极化整格，其秩即可界定顶形式特征的分圆多项式次数。秩界分两步：先对角线爆破上的类用 Hodge 范数变分的维数依赖估计加体积与 Seshadri 下界得到 `@@M@@\dim T(U)@@` 的界；再去掉 Seshadri 假设——小阶移动子簇给出有理纤维化，极大概率纤维化把问题化为垂直 jet 与水平截面计数，用校准的大除子使两个计数同尺度，有限次幂映射论证使水平估计关于层秩线性。最后由特征指数统一杀死所有闭路障碍，完成定理。

## 可信度与备注
主结果尚无 Lean 形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。本文与同族姊妹篇互相咬合：它调用《Uniform Pluricanonical Iitaka Fibrations》的一致正规指标定理与《Log abundance in characteristic zero》的全维数好模型定理作为重大输入，而这些输入本身亦属未形式化之列，核验时需一并追溯。

{% endraw %}
