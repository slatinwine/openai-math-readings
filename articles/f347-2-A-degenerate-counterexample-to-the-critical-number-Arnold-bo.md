---
layout: default
title: "Three fixed points on the symplectic quadric threefold"
family: "347"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Three fixed points on the symplectic quadric threefold

> 结果族 347：Counterexamples to stable-Morse and strong Arnold fixed-point bounds　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在复三维二次超曲面 \(Q^3\)（实六维闭辛流形）上，本文构造出恰好有三个不动点的光滑哈密顿微分同胚，而该流形上任何光滑函数都至少有四个临界点——同时推翻 Arnold 猜想的临界数形式与有理杯长形式，且三是最优计数。

## 问题背景

Arnold 不动点猜想把哈密顿不动点与光滑函数的临界点作比较，其最强（无退化假设）形式断言：闭辛流形上任何哈密顿微分同胚（Hamiltonian diffeomorphism）的不动点数不少于临界数（critical number）\(\Crit(M)\)，即允许退化临界点时所有光滑函数临界点数的最小值；其弱形式用有理杯长（cup length）替代。正结果集中于特殊情形：标准环面（Conley–Zehnder）、\(\CP^n\)（Fortune）、\(\pi_2=0\) 时的杯长界（Hofer）、\([\omega]\) 与 \(c_1\) 在 \(\pi_2\) 上为零（Rudyak–Oprea）。二次超曲面含正辛面积的球面，恰在这些假设之外。Ma 曾断言哈密顿不动点最小个数恒等于 \(\Crit(M)\)；Buhovsky–Humilière–Seyfaddini 只对连续（\(C^0\)）哈密顿同胚造出过单不动点例子。光滑反例此前一直缺失。

## 主要结果

主定理：取 \(Q^3=\{z_0^2+z_1^2+z_2^2+z_3^2+z_4^2=0\}\subset\CP^4\)（带限制 Fubini–Study 辛形式），存在光滑哈密顿微分同胚 \(\phi\) 使

\[\#\Fix(\phi)=3<4=\Crit(Q^3)=\operatorname{cuplength}(Q^3;\mathbb Q),\]

且至少一个不动点退化（degenerate）。三是最优的：Gong 证明复维数 \(n\ge2\) 的标准二次超曲面上任何哈密顿微分同胚至少有 \(n\) 个不动点，本例在 \(n=3\) 时达到该界。由于计数涵盖全部不动点，附加轨道可缩条件也无法挽救不等式；非退化情形的同调 Arnold 不等式涉及不同假设，与本例相容。

## 证明思路

核心机制是"有限阶传递"：设 \(A\) 为 \(m\) 阶哈密顿映射，不动集 \(F\) 是干净不动子流形（clean fixed set，即 \(T_qF=\ker(dA_q-\id)\)）。先把 \(F\) 上的函数 \(f\) 任意延拓，再按有限群平均得到 \(A\)-不变的 \(K\)；平均算子是到 \(T_qF\) 的投影，故 \(K\) 在 \(F\) 处的环境临界性等价于 \(f\) 的临界性（对称临界性原理的有限群特例）。不变性使 \(K\) 的哈密顿流 \(B_s\) 与 \(A\) 交换，于是 \((A\circ B_\varepsilon)^m=B_{m\varepsilon}\)；再用短周期引理（Lipschitz 估计排除短非平凡周期轨，Yorke 定理的初等版本）取足够小的 \(\varepsilon\)，则 \(B_{m\varepsilon}\) 的不动点恰为 \(K\) 的临界点，最终得 \(\Fix(A\circ B_\varepsilon)=\Crit(f)\)——不动点计数被完全转移到子流形上的临界点计数。

载体是二次超曲面上的哈密顿对合（involution）\(A[z_0:\cdots:z_4]=[z_0:-z_1:\cdots:-z_4]\)：它是等速旋转流 \(\Phi_1^{\pi,\pi}\)，显式哈密顿量 \(G_{a,b}\) 保证其哈密顿性；不动集 \(F=Q^3\cap\{z_0=0\}\) 经秩一矩阵实现同构于 \(S^2\times S^2\)，切空间分解为 \(\pm1\) 特征子空间，干净条件成立。

\(F\) 上取显式函数 \(f(x,y)=e\cdot x+(x-p)\cdot y\)（\(p\) 为北极、\(e\) 为赤道点，属 Takens 球面积构造的显式化）。Lagrange 乘子方程可完整解出：得退化孤立临界点 \(q_0=(p,-e)\)（Hessian 特征值 \(1,-1,0,0\)，秩 2）与两个非退化点 \(q_\pm\)（函数值 \(\pm 3\sqrt3/2\)），别无其他。

下界四的验证分两半：Lusternik–Schnirelmann 杯积引理（负梯度流把 \(k\) 个临界值化成 \(k\) 个开覆盖，其上正阶闭形式皆恰当，从而杀死 \(k\) 重杯积）配合超平面类 \(h^3=2[\mathrm{pt}]\ne0\) 给出下界 4；不等速旋转 \(G_{1,2}\) 的临界点是其生成元 \(T=\operatorname{diag}(0,J,2J)\) 的射影特征线，恰有四条落在 \(Q^3\) 上，给出上界 4，两界相等。最后在 \(q_0\) 处：Hessian 核向量 \(v\) 满足 \(DX_f(q_0)v=0\)，故 \(d\phi_{q_0}v=\exp(\varepsilon DX_f(q_0))v=v\)，线性化出现特征值 1，退化性得证。

## 可信度与备注

本文主结果已 Lean 形式化（见结果族 347 的官方 Lean 文档）。姊妹篇在同一结果族中给出十二维、非退化、亏损无界的 Morse 数反例（暂无形式化证明），族内另有单连通闭 Kähler 流形上稳定 Morse 数亏损无界的构造，多篇互补地否定 Arnold 猜想的各无限制形式。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
