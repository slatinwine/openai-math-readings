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

## 一句话结论
论文证明了半对数典范（semi-log-canonical, slc）log Calabi–Yau 配对的一致指标定理：固定维数 \(d\ge4\) 与有限有理系数集 \(\Phi\) 后，存在仅依赖 \(d\) 和 \(\Phi\) 的倍数 \(a(d,\Phi)\)，使 \(a(d,\Phi)(K_X+B)\) 同时 Cartier 且线性平凡，与 \(X\) 的连通分支个数无关。结合 Jiang–Liu 的三维及以下结果，这彻底解决了有限有理系数 slc 指标猜想。

## 问题背景
log Calabi–Yau 配对 \((X,B)\) 满足 \(K_X+B\sim_{\mathbb{Q}}0\)，其指标（index）是使该除子 Cartier 且线丛平凡的最小正整数——它衡量"有理平凡"与"真正平凡"之间的差距。Gongyo 已知这样的指标存在，但可能依赖配对本身；指标猜想（Jiang–Liu 猜想 1.5 的有限有理系数版本）问：固定维数与系数集合后能否有公共倍数。非正规情形另有一层下降（descent）困难：slc 配对允许正规分支沿双重轨迹（double locus）相交，各分支规范化上的平凡化未必在粘合处吻合。这类一致界对模空间理论至关重要——slc 配对正是模问题中极限点的奇性类型。此前 Jiang–Liu 解决了三维及以下和四维非 klt lc 情形，Birkar 解决了有理连通 klt 配对；高维一般 slc 情形悬而未决。值得注意的是 Singh 构造了指标随维数双指数增长的光滑 Calabi–Yau 界，故一致界必须依赖维数。

## 主要结果
定理 1.1：设 \(k\) 为特征零的代数闭域，\(d\ge4\)，\(\Phi\subset[0,1]\cap\mathbb{Q}\) 有限。则存在整数 \(a(d,\Phi)>0\)，使得对任何连通射影等维 slc log Calabi–Yau 配对 \((X,B)\)（维数 \(d\)、\(B\) 的非零系数均属 \(\Phi\)），有 \(a(d,\Phi)(K_X+B)\) Cartier 且 \(\mathcal{O}_X(a(d,\Phi)(K_X+B))\simeq\mathcal{O}_X\)。要点有二：界不依赖 \(X\) 的不可约分支个数与双有理模型上 lc 层的个数；且它是公共平凡化倍数，一次性同时清除局部 Cartier 指标与整体挠。与 Jiang–Liu 三维定理合并，即得有限有理系数 slc 指标猜想的完全解答。

## 证明思路
证明遵循"正规到 slc"的经典策略，先由姊妹篇《Uniform Pluricanonical Iitaka Fibrations》的一致正规指标定理取一个仅依赖 \(d,\Phi\) 的偶数 \(m\)，在每个规范化分支上平凡化表现为带指定对数极点的有理 \(m\)-典范形式 \(\theta_i\)。先在 crepant dlt 模型上取对数留数（logarithmic residue），把它限制到导体（conductor）层上；在一般节点处，两侧留数相差非零标量 \(r_e\)。以规范化分支为顶点、一般节点为边的有限图上，同时匹配所有 \(\theta_i\) 等价于让每条闭路上留数比的乘积为一，因此只需这些乘积的阶一致有界。为此论文把闭路翻译为双有理自同构：极小 lc 层是 klt 的，分支内部用 Kollár 的 \(\mathbb{P}^1\)-链接定理在偶次数下留数不变地连接任意两个极小层，跨边则证明带乘子 \(r_e\) 的双有理留数比较（第 7 节，含非分裂节点与最终 \(S_2\) 延拓）。于是闭路诱导某个极小 klt 层上 crepant 双有理自映射，它作用在平凡化形式上恰为边比之积。问题化归为核心的一致性定理：对满足 \(m(K_V+\Delta)\sim0\) 的射影积分 klt 配对，用 \(\dim V\) 与 \(m\) 界定 crepant 自映射作用于平凡 \(m\)-典范形式的标量阶。这里用 Matsumura–Wang 分解把配对拆成有理连通因子、阿贝尔因子与既约 Calabi–Yau/辛因子：有理连通因子由有界性与多重典范表示控制，其余因子上特征出现在整系数上同调中。具体地考察包含全纯顶形式的极小有理 Hodge 子结构 \(T(U)\subset H^n(U,\mathbb{Q})\)，它双有理不变且带极化整格，其秩即可界定顶形式特征的分圆多项式次数。秩界分两步：先对角线爆破上的类用 Hodge 范数变分的维数依赖估计加体积与 Seshadri 下界得到 \(\dim T(U)\) 的界；再去掉 Seshadri 假设——小阶移动子簇给出有理纤维化，极大概率纤维化把问题化为垂直 jet 与水平截面计数，用校准的大除子使两个计数同尺度，有限次幂映射论证使水平估计关于层秩线性。最后由特征指数统一杀死所有闭路障碍，完成定理。

## 可信度与备注
主结果尚无 Lean 形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。本文与同族姊妹篇互相咬合：它调用《Uniform Pluricanonical Iitaka Fibrations》的一致正规指标定理与《Log abundance in characteristic zero》的全维数好模型定理作为重大输入，而这些输入本身亦属未形式化之列，核验时需一并追溯。

{% endraw %}
