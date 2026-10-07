---
layout: default
title: "A counterexample to integer-degree harmonic dimension comparison"
family: "361"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to integer-degree harmonic dimension comparison

> 结果族 361：Failure of integer-degree harmonic dimension comparison　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文在 \(\mathbb R^{16}\)（一般地，某个偶数维 \(n\geq 8\)）上构造了 \(\operatorname{Ric}\geq 0\) 的完备光滑度量，使增长不超过 \(k=50000\) 的调和函数空间维数严格超过欧氏计数，对丘成桐整数阶调和维数比较问题给出否定回答。

## 问题背景

设 \((M^n,g)\) 是完备的里奇曲率非负（nonnegative Ricci curvature）流形，\(h_k(M,g)\) 记满足逐点增长条件 \(|u(x)|\leq C_u(1+d_g(o,x))^k\) 的实调和函数空间的维数。丘成桐（Yau）在其著名问题清单中问：是否恒有 \(h_k(M,g)\leq h_k(\mathbb R^n,g_{\mathrm E})\)？在欧氏空间上，整数增长 \(k\) 的整体调和函数恰是次数至多 \(k\) 的调和多项式，故 \(h_k(\mathbb R^n,g_{\mathrm E})=\binom{n+k-1}{k}+\binom{n+k-2}{k-1}\)。Li 与 Tam 证明了线性增长的最优界 \(h_1\leq n+1\)；Colding 与 Minicozzi 证明了各阶的有限维性以及随次数增长的最优阶 \(d^{n-1}\)，但固定整数点上的精确欧氏计数始终悬而未决。Donnelly 曾在维数至少 5 时对介于 1 与 2 之间的非整数次数构造反例，可是整数端点上欧氏计数更大，无法直接类推；Cai 与 Lai 则证明附加局部共形平坦假设后严格比较成立。本文在纯 Ricci 假设下否定整数形式的比较。

## 主要结果

**主定理**：存在偶数 \(n\geq 8\) 与整数 \(k\geq 2\)（附录的精确有限谱选取允许取 \(n=16\)、\(k=50000\)），以及 \(\mathbb R^n\) 上一个完备光滑度量 \(g\)，使得 \(\operatorname{Ric}_g\geq 0\) 且

\[h_k(\mathbb R^n,g)>h_k(\mathbb R^n,g_{\mathrm E})=\binom{n+k-1}{k}+\binom{n+k-2}{k-1}.\]

该度量在原点附近是欧氏的，渐近体积比（asymptotic volume ratio）严格介于 0 与 1 之间，在无穷远处的切锥（tangent cone at infinity）不唯一，且不是局部共形平坦（locally conformally flat）的。这些附属几何性质解释了为何此前依赖唯一切锥谱（Huang）或共形平坦（Cai–Lai）的比较定理在此均不适用。

## 证明思路

度量取锥形式 \(g=dr^2+r^2\gamma(\log r)\)，角度量 \(\gamma(t)\) 是奇数维球面 \(S^m\)（\(m=n-1\)）上体积归一化的 Berger 度量 \(G(a,q,J)\)：把 Hopf 方向拉伸 \(q\) 倍再整体缩放 \(a\)，并允许正交复结构 \(J\) 随时间切换。核心思想是"会动的 link"：固定度量锥上，角特征值 \(\lambda\) 只对应唯一的增长指数 \(d\)（\(d(d+m-1)=\lambda\)），而构造让同一个调和函数在多个增长率之间轮流驻留，使其按对数半径平均的增长率严格小于 \(k\)——个别阶段可以超过 \(k\)，只要平均值不超。

先算谱的账。Berger 度量下，\(l\) 次球面调和函数空间 \(V_l\) 上的特征值由 Hopf 荷 \((2b-l)^2\) 决定，其除以 \(l^2\) 后依分布收敛于 \(\mathrm{Beta}(1/2,(m-1)/2)\) 分布。结合一个加权分位数不等式（充分大的奇数 \(m\) 满足 \((m-1)\mathcal J_m>2\)），可以选出方向组：每组的平均指数 \(\overline d_l<k\)，而总数 \(\sum M_l\) 严格超过欧氏计数。

再实现方向交换。在接近圆球的短"脉冲"内切换 \(J\)：迹自由（trace-free）的 Hopf 生成元平方生成直和 \(\bigoplus_{2\leq l\leq L}\mathfrak{sl}(V_l)\)，故可用指数乘积（"字"，word map）同时在各个 \(V_l\) 中实现指定的带符号循环置换，且在字映射微分可逆的参数处取值。

几何排程上，第 \(j\) 个周期由长 \(j^6\) 的脉冲与长 \(j^7\) 的各向异性驻留组成，累计时刻 \(t_j\sim j^8/8\)。径向尺度 \(a\) 的凹形尾巴 \(a'/a=-\mu(1+t)^{-5/4}\) 提供约 \(j^{-10}\) 阶的正径向曲率，压过脉冲各向异性带来的 \(O(j^{-12})\) 负面项；切向分量用 link 的严格 Ricci 下界控制；混合分量因 Hopf 场是等长 Killing 场而为零。曲率估计对一切允许的控制序列一致成立。

传输是技术核心。\(V_l\) 上的调和方程化为矩阵常微分方程，在原点处光滑的"中心正则"解由矩阵 Riccati 方程的解 \(P_l\)（\(Y'=P_lY\)）刻画，正障碍（barrier）保证 \(P_l\) 一致有界，且每个周期起点都重置到 \(\theta_l I+O(j^{-2})\)。整个周期的值传输被精确分解为 \(\mathcal T_{l,j}=s_{l,j}D_{l,j}\Pi_l\)：先分离出长驻留产生的大对角增长 \(D_{l,j}\)（\(\log(D_{l,j})_{ii}\sim j^7d_{l,i}\)），关键引理证明剩余误差乘子一致有界、不随驻留长度放大，最后用压缩映照逐周期把归一化传输精确调到目标循环 \(\Pi_l\)。

最后把循环化为增长估计：置换 \(\Pi_l\) 让所选方向轮转，一整圈的增长贡献恰为均值加权和加上 \(O(J^7)\) 误差，故 \(\log\|Y\|/t\to\overline d_l<k\)；又因每个周期相对 \(t_j\) 可忽略，该界在每个半径处成立。所选函数在球面上限制线性无关，于是维数 \(\geq\sum M_l\) 严格超过欧氏计数。

## 可信度与备注

本篇在任务数据中标注为主结果已 Lean 形式化。同族的姊妹篇进一步把反例降到三维 \(\mathbb R^3\)，对所有充分大的 \(k\) 给出至少 \((k+2)^2\) 个独立调和函数（超过欧氏 \((k+1)^2\)），两篇共享"移动 Berger link＋周期排程＋精确传输"的同一骨架，谱盈余与控制方案互相印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇主定理已属形式化验证范围，姊妹篇则尚待形式化，宜以社区核验为准。

{% endraw %}
