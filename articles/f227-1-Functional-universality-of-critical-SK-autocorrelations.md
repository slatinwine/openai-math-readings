---
layout: default
title: "Functional universality of critical SK autocorrelations"
family: "227"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Functional universality of critical SK autocorrelations

> 结果族 227：Critical SK autocorrelation processes and dynamics across the temperature transition　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

严格证明了 SK 自旋玻璃在临界温度 `@@M@@\beta=1@@` 处的平稳自旋自相关函数在 `@@M@@n^{1/3}@@` 重整与 `@@M@@n^{2/3}@@` 时间尺度下收敛到一个普适的随机泛函极限：高斯与拉德马赫（Rademacher）耦合给出同一极限律，且该极限非退化——样本间随机性被保留。

## 问题背景

平衡自相关衡量系统在平稳动力学下"记住"初始构型多久。SK 模型（Sherrington–Kirkpatrick，1975）在临界温度处记忆的时间尺度随自旋数 `@@M@@n@@` 发散，临界慢化使 `@@M@@n^{2/3}@@` 成为正确的窗口。Billoire–Campbell 2011 年的数值实验早已猜测有限尺寸标度形式 `@@M@@q_c(n,t)\sim n^{-1/3}F(t/n^{2/3})@@`，但无序平均的标度曲线并不能回答单样本曲线是否集中。此前的高温混合结果（如 `@@M@@\beta<1/2@@` 的谱隙与多项式混合）都到不了端点 `@@M@@\beta=1@@`；两篇姊妹手稿分别确定了 `@@M@@n^{2/3}@@` 协方差尺度与匹配的混合指数，但指数陈述本身无法识别固定倍数临界时刻上的动力学。剩下的核心问题是：单样本的整条自相关曲线收敛到什么？极限还随机吗？

## 主要结果

模型为零场 SK 的 Gibbs 测度 `@@M@@\pi_{n,J}(\sigma)\propto\exp\{n^{-1/2}\sum_{i<j}J_{ij}\sigma_i\sigma_j\}@@`，每格点速率为一的热浴（heat-bath）时钟。定义平稳自相关 `@@M@@C_{n,J}(t)=\frac1n\sum_i\langle\sigma_i,P_t^J\sigma_i\rangle_{\pi_{n,J}}@@` 及其临界重整 `@@M@@A_{n,J}(s)=n^{1/3}C_{n,J}(sn^{2/3})@@`。定理证明：存在 `@@M@@C_{\mathrm{loc}}((0,\infty))@@` 上的 Borel 概率律 `@@M@@Q_{\mathrm{crit}}@@`，使得无论 `@@M@@J_{ij}@@` 取高斯还是 `@@M@@\{\pm1\}@@` 均匀（拉德马赫）律，`@@M@@A_{n,J}@@` 都依律收敛到 `@@M@@Q_{\mathrm{crit}}@@`，且收敛在紧正时间区间上一致。`@@M@@Q_{\mathrm{crit}}@@` 不是点质量：它赋予非零、非负、非增且趋于零的函数以概率一；在每个固定正时刻，极限值的支撑无界。极限有显式描述：以 GOE 上边缘过程（edge process）`@@M@@g@@` 为参数，取条件边缘测度（conditioned edge measure）`@@M@@\Pi_g@@`——即方差为 `@@M@@l_a=(g_a+b)^{-1}@@` 的独立高斯坐标在重整平方约束 `@@M@@\sum_a(x_a^2-l_a)=D(b)@@` 下的条件律——上的柱面梯度 Dirichlet 形式，其闭包生成算子 `@@M@@H_\Pi@@`，极限函数为 `@@M@@\mathcal A(s)=\sum_a\langle x_a,e^{-sc_*H_\Pi}x_a\rangle_\Pi@@`，其中 `@@M@@c_*>0@@` 是由一个可定的矩问题（moment problem）刻画的确定性微观系数。

## 证明思路

证明先处理高斯耦合：补一条独立 GOE 对角线不改变 Gibbs 律，于是相互作用矩阵化为 GOE，谱坐标 `@@M@@x=n^{-1/3}U^{\mathsf T}\sigma@@` 分离出上边缘涨落。出发点是预解式迹（resolvent trace）`@@M@@B_n(z)=\sum_a\langle x_a,(z+n^{2/3}H)^{-1}x_a\rangle@@`——它正交基无关，且恰是 `@@M@@A_{n,J}@@` 的拉普拉斯变换，故先证迹收敛、再恢复紧区间上的函数收敛。但平衡收敛不直接够用，原因有二：边缘坐标上的函数可借微小修正降低 Dirichlet 能量；有限个坐标的收敛控制不住自相关中对全部坐标的求和。第一步在尺度 `@@M@@p@@` 处做谱盖帽观测（spectral cap）：把超过 `@@M@@2-p^2@@` 的特征值截平并把截去部分变成观测精度，后验即化为盖帽相互作用加外场；借助 Comets 式特征标架平均把立方体后验均值与球模型鞍点比较，把条件方差界磨到无幂损失的 `@@M@@p^{-2}@@` 阶。第二步证明这些光滑化的斜率收敛为 `@@M@@\Pi@@` 上的弱梯度，其定义域恰为光滑柱面函数的闭包，从而识别出条件测度上的闭能量形式。第三步处理微观修正：固定阶压缩给出 `@@M@@[0,\infty)@@` 上确定性正测度 `@@M@@\omega@@`，多项式逼近分离出其零点原子 `@@M@@c_*=\omega(\{0\})@@`，对极限形式 `@@M@@c_*\int|\nabla F|^2\,d\Pi@@` 同时给出下界与可达的恢复序列。第四步用向量分部积分界住预解式迹的尾部，系数的可和衰减使有限坐标收敛足以控制整个可观测量。最后对拉德马赫耦合做 Lindeberg 型比较：由于可观测量同时依赖 Gibbs 律与生成元，先转移一个由二次自旋特征构造的迹，其消失性恰好控制自旋迹的四阶余项——正是这一阶数的安排让四阶矩不同的两类耦合共享同一极限。

## 可信度与备注

本文主结果无 Lean 形式化证明，属 OpenAI 预印本，官方声明未经形式化的结果可能存在问题，请以社区核验为准。它依赖同族姊妹篇（临界慢化与临界混合两份手稿）提供的 `@@M@@n^{2/3}@@` 尺度与盖帽—球面比较输入，而其识别出的平稳极限 `@@M@@A_g@@`、条件测度 `@@M@@\Pi_g@@` 与系数 `@@M@@c_*@@` 又是淬火姊妹篇《Universality of critical quench autocorrelations》的直接输入，三者在结果族 227 中构成承重链。

{% endraw %}
