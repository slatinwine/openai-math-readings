---
layout: default
title: "The sharp factor-of-IID threshold for the free Ising model on regular trees"
family: "236"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The sharp factor-of-IID threshold for the free Ising model on regular trees

> 结果族 236：The exact factor-of-IID threshold for free Ising spins on trees　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文完全确定了无穷 \(d\)-正则树上自由零场铁磁 Ising 态作为"独立同分布标签的因子"（factor of IID）的精确门槛：当且仅当 \(\tanh\beta\le(d-1)^{-1/2}\)，含临界等号情形。这证明了 Nam–Sly–Zhang 猜想，且构造的因子与每个树自同构在每个输入上交换。

## 问题背景

在无穷图的每个顶点放一个独立均匀标签 \((U_v)\)，用一个与图自同构可交换的可测映射 \(\Phi\) 把整场标签变成自旋场，所得法律称为 factor of IID。Lyons 问：树上的自由 Gibbs 态能否这样"无根地"生成？无穷 \(d\)-正则树上自由零场 Ising 态 \(\mu_{d,\beta}\)（记 \(\theta=\tanh\beta\)，\(b=d-1\)）的广播描述是：任取一点掷公平自旋，沿边让子顶点以 \((1+\theta)/2\) 概率随父——法律与根无关、在全部自同构下不变，但规则里藏着一个根。阈值 \(b\theta^2=1\) 恰是重建阈值（reconstruction threshold）：超过它时自由态不极端，Sly 借 Backhausz–Szegedy–Virág 的相关界证明不可能有因子表示；远低于它（\(\theta\le b^{-1}\)，唯一性区域）Lyons 给出有限簇构造。中间区域连同临界点 \(\theta=b^{-1/2}\) 一直悬置：Nam、Sly、Zhang 用后验漂移随机微分方程证明了大 \(d\)、小 \(\theta\) 时可行，并猜想完整阈值含等号。难点在于：因子法律的弱极限不必是因子，非重建也不提供生成规则，等号情形必须直接构造。

## 主要结果

主定理：对每个整数 \(d\ge3\) 与 \(\beta\ge0\)，自由零场 Ising 法律 \(\mu_{d,\beta}\) 是 factor of IID——存在可测映射 \(\Phi:[0,1]^{\mathcal V}\to\{-1,1\}^{\mathcal V}\)，使对每个固定自同构 \(g\) 几乎必然有 \(\Phi(gU)=g\Phi(U)\)——当且仅当 \(\tanh\beta\le(d-1)^{-1/2}\)。论文证明正向（含等号），严格反向为已知结果。此外 \(\Phi\) 可选成在每个标签输入上与每个自同构逐点交换；论文明确不主张有限半径编码（finitary coding）与编码半径估计。\(\theta=0\) 时法律本就是独立公平符号，平凡成立。

## 证明思路

先搭观察框架（沿用 Nam–Sly–Zhang）：在辅助概率空间采出目标自旋构型 \(\sigma\) 与独立布朗运动，观察 \(X_v(t)=t\sigma_v+B_v(t)\)（属随机定位 stochastic localization 一脉），记后验均值 \(m_v(t)\)，减去条件漂移得新息 \(W_v=X_v-\int_0^t m_v\,ds\)。经典滤波理论保证各 \(W_v\) 是独立布朗运动，但 Brown 性本身不保证 \(X\) 是 \(W\) 的函数，"新息决定观察"是全文枢纽。

再建立无穷新息方程：引入腔场 \(h_{j\to i}\) 与路径响应系数 \(c_{vu}=\theta^r\prod_i a(h_{v_i\to v_{i-1}})\)，其中 \(a(z)=\frac{1-\tanh^2z}{1-\theta^2\tanh^2z}\)，场满足 \(dh_v=\sum_u c_{vu}\,dW_u+m_vA_v\,dt\)，\(A_v=\sum_u c_{vu}^2\)。无穷和的合法性靠"能量不逃逸到边界"：远离零时刻用逐顶点高斯衰减，零时刻附近用整体信息估计 \(\E m_v(t)^2\le C\sqrt t\)（临界时 \(\E A_v(t)\le C/\sqrt t\)），再以精确能量恒等式与检验论证排除残余鞅。

然后做条件副本比较：给定全部新息独立采两个观察副本，证明观察的过去只依赖新息的过去，故 \(W\) 在联合过滤中仍是布朗、两副本由同一列布朗驱动。记 \(V(t)=\E[(h_o-h'_o)^2]\)，\(V(0)=0\)。次临界时壳层大小 \(db^{r-1}\) 与 \(\theta^{2r}\) 之积构成收敛几何级数，得 \(V'\le CV\)，由 Gronwall 不等式得 \(V=0\)。临界点处两因子恰好相消，需三项替补估计：完整侧枝在尺度 \(t^{-1/2}\) 上衰减路径乘积；谱方法空间抵消把 \(\log a\) 因子差之和的方差压到 \(rS(t)\)；路径平均的集中。剩余的小时困难是主导噪声项 \(S(t)/t\) 不可积：利用 \(p\ge3\) 时 \(b\theta^p<1\) 的严格压缩，把二阶矩尺度递归传播成所有整数矩 \(\E|h_{v\to w}|^p\le e^{Kp^2}t^{p/4}\) 与小场尾估计，加上 \((\log a)'\) 在原点为零，改进 \(S\) 与 \(V\) 的比较，最终得 Osgood 型不等式 \(V'\le k_T(t)V(1+\log(K_T/V))\)，系数 \(k_T\) 可积，迫使 \(V\equiv0\)。

最后恢复：副本相等说明给定新息的条件法律是点质量，存在 Borel 映射 \(F\) 使 \(X=F(W)\)；整时斜率 \(X_v(n)/n\to\sigma_v\) 几乎必然，自旋从新息读出；把均匀标签经 Borel 采样变为布朗路径得到因子，再用有限球条件期望平均升级为逐点等变版本。

## 可信度与备注

任务元信息标注该主结果已有 Lean 形式化证明（族内文档 lean/docs/236.md）；反向障碍出自 Sly 并使用 BSV 相关界，为已知结果。文内引用的同系列自由均匀生成树森林（FUSF）姊妹篇用一致 Lipschitz 响应界因果反演新息，本篇改走条件副本相等性路线，方法互补。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇主结果已形式化，其余技术细节仍以论文与社区核验为准。

{% endraw %}
