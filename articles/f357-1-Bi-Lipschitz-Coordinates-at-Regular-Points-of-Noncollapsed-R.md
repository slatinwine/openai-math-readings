---
layout: default
title: "Bi-Lipschitz Coordinates at Regular Points of Noncollapsed RCD Spaces"
family: "357"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bi-Lipschitz Coordinates at Regular Points of Noncollapsed RCD Spaces

> 结果族 357：Bi-Lipschitz coordinates at every regular RCD point　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在参考测度恰为 `@@M@@\mathcal H^n@@` 的非坍缩 `@@M@@\mathrm{RCD}(K,n)@@` 空间中，每个正则点（所有切空间均为欧氏空间）都有开邻域双 Lipschitz（bi-Lipschitz）同胚于 `@@M@@\mathbb R^n@@` 的开集，畸变常数只依赖维数 `@@M@@n@@`——解决了 Honda–Zhang 明确重述的正则点双 Lipschitz 坐标猜想。

## 问题背景

对带 Ricci 曲率下界的黎曼流形取极限，所得度量空间远比流形粗糙。Lott–Villani 与 Sturm 借最优传输（optimal transport）提出 `@@M@@\mathrm{CD}@@` 条件，经 Ambrosio–Gigli–Savaré 的黎曼细化与 Erbar–Kuwada–Sturm 的 Bochner 不等式，形成 `@@M@@\mathrm{RCD}(K,n)@@` 空间理论：它以综合方式表达"Ricci 曲率 `@@M@@\ge K@@`、维数 `@@M@@\le n@@`"；非坍缩（noncollapsed）指参考测度恰为 `@@M@@n@@` 维 Hausdorff 测度。Cheeger–Colding 研究非坍缩 Ricci 极限空间时已得到流形邻域的双 Hölder（bi-Hölder）参数化，并明确追问能否升级为双 Lipschitz；此后 Mondino–Naber 证明 RCD 空间的可数双 Lipschitz 可矩形化（rectifiability，覆盖几乎所有点），Kapovitch–Mondino 把正则集包进带双 Hölder 图卡的开流形区域，但"每个指定正则点都有双 Lipschitz 图卡"这一猜想（Honda–Zhang 于 2026 年明确重述）一直未决。症结在于：切空间欧氏只是逐尺度的无穷小陈述，而图卡必须同时比较邻域内所有点对，需要跨无穷多个尺度的均匀控制，且调和坐标（harmonic coordinates）的度量张量可能以未知速率退化。

## 主要结果

主定理：对每个整数 `@@M@@n\ge2@@` 存在常数 `@@M@@L_n\ge1@@`，使得对任意 `@@M@@K\in\mathbb R@@` 与任意非坍缩 `@@M@@\mathrm{RCD}(K,n)@@` 空间 `@@M@@(X,d,\mathcal H_d^n)@@`，若点 `@@M@@p@@` 处所有带基点的 Gromov–Hausdorff 切空间（pointed tangent）都带基点等距于 `@@M@@(\mathbb R^n,|\cdot|,0)@@`（即 `@@M@@p@@` 为 `@@M@@n@@`-正则点），则存在开邻域 `@@M@@U\ni p@@`、开集 `@@M@@V\subset\mathbb R^n@@` 及同胚 `@@M@@F:U\to V@@`，满足

`@@M@@DL_n^{-1}d(x,z)\le|F(x)-F(z)|\le L_nd(x,z),\qquad x,z\in U,@@`

其中距离是限制在 `@@M@@U@@` 上的环境距离（ambient distance）。畸变常数只依赖维数，与 `@@M@@K@@`、空间和点均无关；邻域可依赖 `@@M@@X@@` 与 `@@M@@p@@`。定理对每个指定的正则点成立，而非仅对参考测度几乎处处的点。推论：全体 `@@M@@n@@`-正则点含于一个开集 `@@M@@\mathcal U@@`（其余集 `@@M@@\mathcal H^n@@`-零测），`@@M@@\mathcal U@@` 上存在可数多个 `@@M@@L_n@@`-双 Lipschitz 图卡构成的图册（atlas），转移映射为 `@@M@@L_n^2@@`-双 Lipschitz。注意结论不断言图卡中度量张量的 Hölder 连续性——Colding–Naber 的反例表明那在一般情形本就无望。

## 证明思路

先在 `@@M@@p@@` 处作趋于零的伸缩 `@@M@@s_\nu^{-1}d@@`。正则性保证子列按带基点 Gromov–Hausdorff 意义收敛到 `@@M@@\mathbb R^n@@`，非坍缩体积收敛认定极限测度为 `@@M@@\mathcal H^n@@`，于是得到一列"越来越平坦"的空间；在其上构造逼近欧氏坐标函数的调和坐标列 `@@M@@u=(u_1,\dots,u_n)@@`，梯度一致有界，且 `@@M@@u@@` 是到 `@@M@@\mathbb R^n@@` 开集的同胚。但 `@@M@@u@@` 的 Gram 矩阵场 `@@M@@G=(\langle\nabla u_j,\nabla u_k\rangle)@@` 随尺度可能退化且速率不可控——这正是双 Hölder 与双 Lipschitz 之间的鸿沟。作者的破解是两条互补的估计。

第一条管"累积"。用热半群在时间 `@@M@@r_i^2=4^{-i}@@` 的平均 `@@M@@Q_i@@` 替换 `@@M@@G@@` 的球平均，使逆矩阵 `@@M@@H_i=Q_i^{-1}@@` 随尺度单调增；Bochner 测度（Bochner measure）`@@M@@M=\tfrac12\Delta G+\kappa G\mathfrak m@@` 的球质量经两次 Gram 逆矩阵共轭后记为 `@@M@@D_{i,y}@@`。核心的"累积比较"引理给出 `@@M@@\mathrm{Id}+\sum_{i<k}Z_i\le C_*H_k@@` 及反向不等式，全程不要求不同尺度的矩阵可交换；`@@M@@H_i@@` 允许无界增长，它恰好记账坐标需要被拉伸的总量。

第二条管"方向"。把同一 `@@M@@D_{i,y}@@` 作用在真实坐标差上：`@@M@@D_{i,y}[u(x)-u(z)]\le Cr_i^2(E_i(x)+E_i(z))@@`，且 `@@M@@\sup_x\sum_iE_i(x)\to0@@`。证明用平方距离的 Poisson 替换（Poisson replacement，承接 Cheeger–Colding 的近刚性方法），缺陷的可和性由 Bishop–Gromov 体积比较沿二进尺度伸缩求和而得；双中心情形经交换子计算把两替换之差的径向导数与坐标差挂钩，再以"尖锐投影"把该差投射到调和坐标张成的仿射函数上，其中径向传输（radial transport）论证用满足符号条件的指数截断保住缺陷的平方结构，最后的紧性反证把问题化为欧氏极限中算子 `@@M@@X\cdot\nabla-1@@` 逐齐次分量放大 `@@M@@q-1@@` 倍的特征值论证。

最后是纯解析的"坐标值空间重整化"：在开值域 `@@M@@\Omega=u(B_1(p))@@` 上用 `@@M@@D_{i,y}@@` 与 Gevrey 型截断构造光滑余向量场 `@@M@@v_i@@`，迭代 `@@M@@h_{i+1}=h_i+Dh_i^{-T}v_i@@`。拉回度量的主增量恰是 `@@M@@D_{i,y}@@` 的正和；误差中的对角二阶导数满足递推 `@@M@@b_{i+1}\le\tfrac12b_i+C_Af_i@@`，故 `@@M@@\sum_i b_i^2@@` 收敛，经 Cauchy–Schwarz 后只需 `@@M@@\sum_iE_i@@` 可和——即使 `@@M@@\sum_i\sqrt{E_i}@@` 发散迭代也能闭合，同时维持度量 Bootstrap 不等式 `@@M@@A^{-1}H_i\le J_i^TJ_i\le AH_i@@`；各阶导数按 Gevrey 速率增长的界由一个阶乘卷积引理在矩阵求逆时保持。极限 `@@M@@F=\lim_i h_i\circ u@@` 沿值空间线段作 Taylor 展开即得双 Lipschitz 双侧估计，像的开性由区域不变性（invariance of domain）得到，最终 `@@M@@L_n=4\sqrt{A(n)}@@` 只依赖 `@@M@@n@@`。

## 可信度与备注

本文是 OpenAI 于 2026 年 9 月发布的预印本，主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。证明自成体系：调和坐标、热平均与累积比较、可和方向夹挤、值空间迭代四章环环相扣，关键命题均附完整证明，且与 Mondino–Naber、Kapovitch–Mondino、Honda–Zhang 等前人结果的强弱边界交代清晰。本文即结果族 357 的核心论文，定理陈述与族概述一致；文中也如实指出结论不涉及度量张量的 Hölder 正则性，也不断言坐标分量的 Laplace 有界性。

{% endraw %}
