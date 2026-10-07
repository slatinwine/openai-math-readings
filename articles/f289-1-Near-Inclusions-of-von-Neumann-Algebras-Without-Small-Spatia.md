---
layout: default
title: "Near Inclusions of von Neumann Algebras Without Small Spatial Embeddings"
family: "289"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Near Inclusions of von Neumann Algebras Without Small Spatial Embeddings

> 结果族 289：Strong Kadison–Kastler stability and its spatial boundaries　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对 Cameron–Christensen–Sinclair–Smith–White–Wiggins 提出的无限制单侧近包含问题给出否定回答：构造了一列可分 Hilbert 空间上的 von Neumann 代数对，单侧间隙 `@@M@@\gamma(M_n,N_n)\to 0@@`，但任何实现 `@@M@@uM_nu^*\subseteq N_n@@` 的酉算子都满足 `@@M@@\|u-I\|\ge\varepsilon_0>0@@`。

## 问题背景

Christensen 在 1980 年引入了近包含（near inclusion）：单侧间隙 `@@M@@\gamma(M,N)=\sup_{\|x\|\le 1,\,x\in M}\inf_{y\in N}\|x-y\|@@` 度量"`@@M@@M@@` 的每个收缩元都被 `@@M@@N@@` 中某元逼近"（逼近元不必是收缩元）。若酉算子 `@@M@@u@@` 使 `@@M@@uMu^*\subseteq N@@`，则 `@@M@@\gamma(M,N)\le 2\|u-I\|@@`；Christensen 证明了当源代数可均时，此不等式在某种程度上可逆——小的近包含可被小的实现酉元兑现。Cameron–Christensen–Sinclair–Smith–White–Wiggins 在 2012 年提出无限制的单侧问题：是否存在一致的 `@@M@@\delta(\varepsilon)>0@@`，使 `@@M@@\gamma(M,N)<\delta@@` 蕴含存在 `@@M@@\|u-I\|<\varepsilon@@` 的实现酉元，且 `@@M@@\delta@@` 与代数及其表示无关？此前的正向方法全部依赖可均性或双边假设，非均源代数上一筹莫展。

## 主要结果

**定理**：存在 `@@M@@\varepsilon_0>0@@`、可分复 Hilbert 空间 `@@M@@H_n@@` 与共单位元 `@@M@@I_{H_n}@@` 的 von Neumann 代数 `@@M@@M_n,N_n\subseteq\mathcal B(H_n)@@`，使得 `@@M@@\gamma(M_n,N_n)\to 0@@`，但对所有充分大的 `@@M@@n@@`，每个满足 `@@M@@uM_nu^*\subseteq N_n@@` 的酉算子（unitary）都满足 `@@M@@\|u-I_{H_n}\|\ge\varepsilon_0@@`。值得强调：这些例子中空间嵌入确实存在（构造里的对角酉算子 `@@M@@W@@` 本身就实现 `@@M@@W^*MW\subset N@@`），障碍纯粹在于"实现嵌入的酉元不能小"。定理的假设是单侧的：构造不提供反向近包含，因而不与本族第一篇的双边正定理冲突，也不触及 CCSSWW 在附加结构假设下关于非均因子的正结果——那些是不同的命题。

## 证明思路

种子是 Voiculescu 1983 年的钟–移矩阵（clock and shift matrices）`@@M@@U_n,V_n@@`：`@@M@@\|U_nV_n-V_nU_n\|\to 0@@`，但它们不能被交换的酉矩阵对逼近。障碍是 Exel–Loring 的绕数（winding number）不变量 `@@M@@\kappa(U,V)=\frac{1}{2\pi i}\mathrm{Tr}\log(UVU^*V^*)@@`：由行列式恒等式它是整数，钟–移对取值 `@@M@@1@@`、交换对取值 `@@M@@0@@`，而沿途中保持对数有定义的路径连续，故二者不可接近。论文要把这个有限维障碍移植进近包含问题。第一步，在可数生成自由群 `@@M@@\mathbb F@@` 上构造带圆参数 `@@M@@z@@` 的 Pytlik–Szwarc 表示：在 Cayley 树上递归定义 `@@M@@\xi_x=t\xi_{p(x)}+r\delta_x@@`，其 Gram 矩阵 `@@M@@\langle\xi_x,\xi_y\rangle=t^{d(x,y)}@@` 保证 `@@M@@\pi(g)\xi_x=\xi_{gx}@@` 扩成酉表示；再用满同态 `@@M@@q:\mathbb F\to\mathbb Z@@`（`@@M@@q(s_j)=1@@`）扭曲得 `@@M@@\pi_z@@`，其 Fourier 系数 `@@M@@A_k(g)@@` 满足一致界 `@@M@@c_k@@`，且零阶与一阶矩都可和——这是后续估计的命脉。关键极限是：沿互不相同的生成元 `@@M@@s_j@@`，`@@M@@\pi_z(s_j)@@` 弱收敛于 `@@M@@tz\,p_e@@`。第二步把 `@@M@@z@@` 换成矩阵：`@@M@@a(g)=\sum_kA_k(g)\otimes I\otimes U^k@@` 与 `@@M@@b(g)=\sum_k I\otimes A_k(g)\otimes V^k@@` 都是酉表示，其弱极限分别保留 `@@M@@U@@` 与 `@@M@@V@@`。在 `@@M@@G=\mathbb F\times\mathbb F@@` 上令 `@@M@@f(x)=a(x_1)b(x_2)@@`，作对角酉算子 `@@M@@W@@`，并定义 `@@M@@M=W(\lambda(G)''\otimes I)W^*@@`、`@@M@@N=(\rho(G)\otimes I)'@@`；恒有 `@@M@@W^*MW\subset N@@`，故嵌入总是存在。近包含估计的关键在换序：`@@M@@\lambda(G)''@@` 中元素的矩阵系数在共同右平移下不变，把 `@@M@@W(X\otimes I)W^*@@` 的算子块 `@@M@@X_{x,y}\,a(x_1)b(x_2)b(y_2)^*a(y_1)^*@@` 重排为 `@@M@@X_{x,y}\,f(xy^{-1})@@` 即得 `@@M@@N@@` 中逼近元，而两种排列的差可用 Fourier 展开与幂次换位子估计 `@@M@@\|U^aV^b-V^bU^a\|\le|a|\,|b|\,\|UV-VU\|@@` 控制，误差被 `@@M@@C\|UV-VU\|@@` 一致界定，且对源代数的整个单位球成立——系数界 `@@M@@c_k@@` 的一阶矩可和性在此不可缺。第三步反证：设存在 `@@M@@u_n\to I@@` 实现嵌入，则 `@@M@@\Sigma_n(g)=u_nW_n(\lambda(g)\otimes I)W_n^*u_n^*(\rho(g)\otimes I)@@` 是 `@@M@@G@@` 的酉表示，其两个因子生成的 von Neumann 代数交换；沿 `@@M@@s_j@@` 取弱极限，可从 `@@M@@\Sigma_n@@` 中恢复出接近 `@@M@@U_n,V_n@@` 的、支在投影上的拷贝；再经一条"角引理"（把支投影换成交换代数中的邻近投影、压缩到公共有限维角、取极部分）得到逼近钟–移对的交换酉矩阵，与绕数障碍矛盾。于是不存在任何子列使其实现酉元趋于恒等，这正意味着对充分大的 `@@M@@n@@`，所有实现酉元与恒等算子的距离有一个公共的正下界 `@@M@@\varepsilon_0@@`。

## 可信度与备注

本篇反例恰好说明结果族 289 第一篇正定理的双边假设不可削弱为单侧：双边接近时近恒等共轭总是存在，单侧逼近则可能彻底失败。与第三篇（可分 `@@M@@C^*@@`-反例）一起，两篇反例从两侧划定了稳定性成立的空间边界。主结果暂无 Lean 形式化证明；OpenAI 官方声明未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
